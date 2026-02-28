# app--icms-cte

🚛 Calculadora de ICMS para CT-e (Logística Brasil)

Este é um sistema web completo e moderno para simulação de cálculo de ICMS em operações de transporte de cargas (CT-e) no Brasil. O sistema calcula automaticamente o imposto, sugere o CFOP e determina o valor total do frete com base nas regras de tributação interestadual e estadual.
🚀 Funcionalidades

    Cálculo de ICMS "Por Dentro": Realiza o cálculo tributário conforme a legislação brasileira, onde o imposto integra sua própria base de cálculo.

    Matriz de Alíquotas Dinâmica: Identifica se a operação é interna (mesmo estado) ou interestadual, aplicando as alíquotas de 7%, 12% ou alíquota interna.

    Sugestão de CFOP: Sugere automaticamente os códigos 5353 (estadual) ou 6353 (interestadual).

    Interface Responsiva: Frontend leve construído com CSS3 puro e interatividade via Alpine.js.

    Arquitetura Limpa: Backend estruturado com FastAPI utilizando padrões de Services e Schemas para fácil manutenção.

🛠️ Tecnologias Utilizadas

    Backend: FastAPI (Python 3.9+)

    Validação de Dados: Pydantic

    Frontend: HTML5, CSS3 Moderno e Alpine.js

    Servidor ASGI: Uvicorn



🔧 Instalação e Execução

1. Clonar o repositório
code Bash

git clone https://github.com/seu-usuario/calculadora-icms-cte.git
cd calculadora-icms-cte


2. Configurar o Backend

Recomenda-se o uso de um ambiente virtual:
code Bash

# Criar ambiente virtual
python -m venv venv

# Ativar ambiente (Windows)
venv\Scripts\activate

# Ativar ambiente (Linux/Mac)
source venv/bin/activate

# Instalar dependências
pip install fastapi uvicorn


3. Rodar o Servidor
   
code Bash

cd backend
uvicorn main:app --reload

O backend estará disponível em: http://127.0.0.1:8000
A documentação interativa (Swagger) pode ser acessada em: http://127.0.0.1:8000/docs
4. Acessar o Frontend

Basta abrir o arquivo frontend/index.html em qualquer navegador moderno.
📝 Regras de Negócio Implementadas

    Operação Interna: Quando Origem = Destino. Alíquota padrão aplicada: 18%.

    Operação Interestadual:

        Origem (Sul/Sudeste) para Destino (Norte/Nordeste/Centro-Oeste/ES): 7%.

        Demais operações interestaduais: 12%.

    Fórmula do Cálculo: Valor Total = Valor Frete / (1 - (Alíquota / 100))

Desenvolvido para fins de simulação logística e automação fiscal.

