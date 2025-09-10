# tatianalisson.github.io
Site Interface Relacionamento Cliente 
from flask import Flask, render_template, request, jsonify

app = Flask(__name__)

# Disciplinas e seus preços
courses = {
    "Algoritmos": 100,
    "Python": 120,
    "Java": 130,
    "DOS": 80,
    "Fortran": 90,
    "História dos Computadores": 110,
    "História das Máquinas de Calcular": 85,
    "História dos Cálculos": 95,
}

@app.route('/')
def index():
    return render_template('index.html', courses=courses)

@app.route('/process_payment', methods=['POST'])
def process_payment():
    data = request.json
    selected_courses = data.get('selected_courses', [])
    card_number = data.get('card_number', '')
    if not selected_courses or not card_number:
        return jsonify({'success': False, 'message': 'Selecione pelo menos uma disciplina e informe o número do cartão.'})
    # Aqui poderia ser implementado processamento real de pagamento
    return jsonify({'success': True, 'message': 'Pagamento realizado com sucesso!', 'selected_courses': selected_courses})

if __name__ == '__main__':
    app.run(debug=True)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8" />
    <title>Microempresa - Cursos</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            display: flex;
        }
        #menu {
            width: 250px;
            background: #f0f0f0;
            height: 100vh;
            padding: 20px;
            box-sizing: border-box;
            border-right: 1px solid #ccc;
        }
        #menu button {
            display: block;
            width: 100%;
            margin-bottom: 10px;
            padding: 10px;
            border: none;
            background: #ddd;
            cursor: pointer;
            text-align: left;
            font-size: 16px;
        }
        #menu button.active {
            background: #bbb;
        }
        #content {
            flex-grow: 1;
            padding: 20px;
        }
        #cart {
            margin-top: 20px;
            border-top: 1px solid #ccc;
            padding-top: 10px;
        }
        label {
            margin-right: 10px;
        }
    </style>
</head>
<body>
    <div id="menu">
        <h3>Disciplinas</h3>
        {% for course, price in courses.items() %}
            <button data-course="{{ course }}" data-price="{{ price }}">{{ course }} - R$ {{ price }}</button>
        {% endfor %}
    </div>

    <div id="content">
        <h2>Selecione a disciplina</h2>
        <div id="selection" style="margin-bottom: 20px;"></div>

        <div id="cart">
            <h3>Carrinho de Compras</h3>
            <ul id="cart-list"></ul>

            <label><input type="checkbox" id="finalize-check" /> Finalizar Compra</label>
            <div id="payment-section" style="display:none; margin-top:10px;">
                <label for="card-number">Número do Cartão:</label>
                <select id="card-number">
                    <option value="">Selecione o cartão</option>
                    <option value="1234 5678 9012 3456">1234 5678 9012 3456</option>
                    <option value="9876 5432 1098 7654">9876 5432 1098 7654</option>
                </select>
                <button id="pay-btn">Pagar</button>
            </div>
            <div id="message" style="margin-top:10px; color:green;"></div>
        </div>
    </div>

    <script>
        const menuButtons = document.querySelectorAll('#menu button');
        const selectionDiv = document.getElementById('selection');
        const cartList = document.getElementById('cart-list');
        const finalizeCheck = document.getElementById('finalize-check');
        const paymentSection = document.getElementById('payment-section');
        const payBtn = document.getElementById('pay-btn');
        const cardNumberSelect = document.getElementById('card-number');
        const messageDiv = document.getElementById('message');

        let selectedCourse = null;
        let cart = [];

        menuButtons.forEach(btn => {
            btn.addEventListener('click', () => {
                menuButtons.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                selectedCourse = btn.getAttribute('data-course');
                const price = btn.getAttribute('data-price');
                showSelection(selectedCourse, price);
                messageDiv.textContent = '';
            });
        });

        function showSelection(course, price) {
            selectionDiv.innerHTML = `
                <p>${course} - R$ ${price}</p>
                <label><input type="radio" name="select-course" value="sim"> Sim</label>
                <label><input type="radio" name="select-course" value="nao" checked> Não</label>
            `;
            const radios = document.getElementsByName('select-course');
            radios.forEach(radio => {
                radio.addEventListener('change', (e) => {
                    if(e.target.value === 'sim') {
                        addToCart(course, price);
                    } else {
                        removeFromCart(course);
                    }
                });
            });
        }

        function addToCart(course, price) {
            if (!cart.find(item => item.course === course)) {
                cart.push({course, price: Number(price)});
                updateCart();
            }
        }

        function removeFromCart(course) {
            cart = cart.filter(item => item.course !== course);
            updateCart();
        }

        function updateCart() {
            cartList.innerHTML = '';
            if (cart.length === 0) {
                cartList.innerHTML = '<li>O carrinho está vazio.</li>';
            } else {
                cart.forEach(item => {
                    let li = document.createElement('li');
                    li.textContent = `${item.course} - R$ ${item.price}`;
                    cartList.appendChild(li);
                });
            }
        }

        finalizeCheck.addEventListener('change', () => {
            paymentSection.style.display = finalizeCheck.checked ? 'block' : 'none';
            messageDiv.textContent = '';
        });

        payBtn.addEventListener('click', () => {
            if(cart.length === 0) {
                alert('Adicione pelo menos uma disciplina ao carrinho!');
                return;
            }
            if(!cardNumberSelect.value) {
                alert('Selecione o número do cartão!');
                return;
            }
            fetch('/process_payment', {
                method: 'POST',
                headers: {'Content-Type': 'application/json'},
                body: JSON.stringify({
                    selected_courses: cart,
                    card_number: cardNumberSelect.value
                })
            })
            .then(resp => resp.json())
            .then(data => {
                if(data.success) {
                    messageDiv.style.color = 'green';
                    messageDiv.textContent = data.message;
                    cart = [];
                    updateCart();
                    finalizeCheck.checked = false;
                    paymentSection.style.display = 'none';
                } else {
                    messageDiv.style.color = 'red';
                    messageDiv.textContent = data.message;
                }
            });
        });

        updateCart();
    </script>
</body>
</html>
