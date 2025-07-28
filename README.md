 🚗 API REST - Controle de Acesso de Veículos no Condomínio

Esta API em Python (Flask) permite **registrar automaticamente a entrada de veículos no condomínio através de câmera e OCR**, 
bem como realizar o **controle completo dos veículos cadastrados**, com autenticação protegida via **JWT** e histórico de alterações.

---

Regra:
Se placa do veículo identificado não estiver no Cadastro de Veículos, cadastrar automaticamente placa e data do cadastro automatico. registrar tambem sua entrada com data e hora automatico.
Se placa do veiculo não identificado Cadastrar Manualmente no Cadastro de Veículos, cadastrar com placa e data do cadastro automatico. registrar tambem sua entrada com data e hora automatico.
---

## 🔧 Funcionalidades

### 📸 Reconhecimento de Placa via OCR
- Captura de imagem via câmera com OpenCV.
- Leitura da placa com EasyOCR.
- Registro automático da entrada do veículo se ele já estiver cadastrado.

### 📥 Registro de Entrada
- `POST /entradas`: Registra a entrada de um veículo (autenticado)
- `GET /entradas`: Lista todas as entradas
- `GET /entradas/<placa>`: Lista entradas de uma placa específica

### 🚗 CRUD de Veículos
- `POST /veiculos`: Cadastra um novo veículo
- `GET /veiculos`: Lista todos os veículos
- `GET /veiculos/<placa>`: Consulta um veículo por placa

### 🔐 Autenticação
- `POST /login`: Gera token JWT para autenticação

---

## ⚙️ Tecnologias utilizadas

- Python 3
- Flask
- Flask-SQLAlchemy
- SQLite (pode ser substituído por PostgreSQL)
- JWT (via PyJWT)
- OCR com EasyOCR + OpenCV
