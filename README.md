# 📡 Network Monitor Desktop App

Aplicativo desktop multiplataforma para **monitoramento de dispositivos em rede local**, **teste de velocidade da internet** e **detecção de dispositivos conectados**, desenvolvido com:

- 🔥 **Frontend**: React + Vite  
- 🐍 **Backend**: Flask + Python (compilado em `.exe`)  
- 🧠 **Monitoramento**: nmap, speedtest, psutil, sqlite3  
- 🖥️ **Empacotamento**: Electron + Electron Builder  

---

## 🚀 Funcionalidades

- Descoberta de dispositivos conectados na rede local via Nmap.
- Teste de velocidade de internet utilizando Speedtest CLI.
- Registro e leitura de dados de dispositivos usando SQLite.
- Interface moderna e responsiva feita com React.
- Aplicação 100% standalone (funciona sem Python ou dependências externas).

---

## 🛠 Estrutura do Projeto

monitor_rede/
│
├── backend/ # Backend Flask (compilado com PyInstaller)
│ └── app.py, monitor.py, speedtest_module.py ...
│
├── frontend/ # Interface React com Vite
│ └── dist/ # Pasta gerada após build
│
├── electron/ # Configuração do Electron
│ ├── bin/ # Executáveis do backend
│ └── main.js # Entry point do Electron
│
├── monitoramento.db # Banco de dados SQLite
└── README.md

## 🧱 Build do Projeto

### 🔧 Pré-requisitos

- Node.js instalado  
- Python 3.x (para desenvolvimento e compilação)  
- `nmap.exe` e `speedtest.exe` devem estar incluídos em `electron/bin/`  

---

### ✅ Etapas para Build e Empacotamento

1. **Build do Frontend (React + Vite)**  
```bash
cd frontend
npm install
npm run build
Build do Backend (Flask com PyInstaller)


cd backend
pyinstaller --onefile app.py
pyinstaller --onefile monitor.py
pyinstaller --onefile speedtest_module.py
⚠️ Copie os arquivos .exe gerados para electron/bin/

Empacotar com Electron Builder


cd electron
npm install
npm run build
🔁 Script de Build Automatizado (Opcional)
Adicione ao package.json dentro da pasta electron:


"scripts": {
  "build:all": "cd ../frontend && npm run build && cd ../backend && pyinstaller --onefile app.py && pyinstaller --onefile monitor.py && pyinstaller --onefile speedtest_module.py && cd ../electron && npm run build"
}
Agora basta rodar:


npm run build:all
💻 Instalação em Outras Máquinas
O aplicativo funciona sem necessidade de Python, Nmap ou Speedtest instalados. Apenas certifique-se de que o instalador final inclua:

app.exe, monitor.exe, speedtest_module.exe

monitoramento.db

nmap.exe

Todos em electron/bin/

🧑‍💻 Desenvolvedores
Josué Marcos Kassoma Manuel
LinkedIn

Garcia Daniel José

📄 Licença
Este projeto é livre para fins educacionais e de demonstração. Contribuições são bem-vindas!
