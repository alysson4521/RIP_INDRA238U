git init
git add .
git commit -m "1.0"
git branch -M main
git remote add origin https://github.com/alysson4521/RIP_INDRA238U.git
git push -u origin main

class ApiClient {
  constructor(baseUrl, token = null) {
    this.baseUrl = baseUrl;
    this.token = token;
  }

  async get(endpoint) {
    const response = await fetch(`${this.baseUrl}${endpoint}`, {
      method: 'GET',
      headers: {
        'Content-Type': 'application/json',
        ...(this.token && { 'Authorization': `Bearer ${this.token}` })
      }
    });

    if (!response.ok) {
      throw new Error(`Erro na requisição: ${response.status}`);
    }

    return await response.json();
  }

  async post(endpoint, data) {
    const response = await fetch(`${this.baseUrl}${endpoint}`, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        ...(this.token && { 'Authorization': `Bearer ${this.token}` })
      },
      body: JSON.stringify(data)
    });

    return await response.json();
  }
}

// Exemplo de uso:
// const api = new ApiClient('https://api.exemplo.com');
// api.get('/usuarios').then(console.log);

import socket

def iniciar_cliente(host='127.0.0.1', port=65432):
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as client_socket:
        client_socket.connect((host, port))
        
        mensagem = "Olá, servidor!"
        client_socket.sendall(mensagem.encode('utf-8'))
        
        resposta = client_socket.recv(1024)
        print(f"Resposta do servidor: {resposta.decode('utf-8')}")

if __name__ == "__main__":
    iniciar_cliente()

    from datetime import datetime

class Cliente:
    def __init__(self, id_cliente: int, nome: str, email: str):
        self.id_cliente = id_cliente
        self.nome = nome
      
        self.criado_em = datetime.now()

    def exibir_dados(self):
        return f"Cliente #{self.id_cliente}: {self.nome} ({self.email})"

# Exemplo de uso:
# novo_cliente = Cliente(1, "Maria Silva", "maria@email.com")
# print(novo_cliente.exibir_dados())

(https://github.com/alysson4521/CLIENT JAVA/releases/download/v1.0.0/meuclient-1.0.0.jar)
