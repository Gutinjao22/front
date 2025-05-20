component.ts

import { Component } from '@angular/core';

@Component({
  selector: 'app-chat',
  templateUrl: './chat.component.html',
  styleUrls: ['./chat.component.css']
})
export class ChatComponent {
  mensagens: { autor: 'atendente' | 'voce', texto: string }[] = [
    { autor: 'atendente', texto: 'Bom dia, tudo certo?' },
    { autor: 'atendente', texto: 'Como posso te ajudar hoje?' },
    { autor: 'voce', texto: 'Bom dia, tudo certo!' },
    { autor: 'voce', texto: 'gostaria de fazer um pedido' },
  ];

  novaMensagem: string = '';

  enviarMensagem() {
    const texto = this.novaMensagem.trim();
    if (!texto) return;

    this.mensagens.push({ autor: 'voce', texto });
    this.novaMensagem = '';

    setTimeout(() => {
      const chatInner = document.querySelector('.chat-inner');
      if (chatInner) {
        chatInner.scrollTop = chatInner.scrollHeight;
      }
    });
  }
}

component.html
<div class="chat-container">
  <div class="header">Atendimento on-line</div>

  <div class="chat-inner">
    <div *ngFor="let msg of mensagens" [ngClass]="['message', msg.autor]">
      <strong>{{ msg.autor === 'atendente' ? 'Atendente diz:' : 'Você diz:' }}</strong>
      <div class="message-box">{{ msg.texto }}</div>
    </div>
  </div>

  <div class="input-box">
    <input
      type="text"
      placeholder="Digite sua mensagem..."
      [(ngModel)]="novaMensagem"
      (keydown.enter)="enviarMensagem()"
    />
    <button (click)="enviarMensagem()">ENVIAR</button>
  </div>
</div>

componente.css

body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: white;
}
.chat-container {
    width: 500px;
    height: 600px;
    border: 3px solid black;
    background-color: white;
    display: flex;
    flex-direction: column;
    position: relative;
}
.header {
    background-color: white;
    border: 2px solid black;
    font-weight: bold;
    color: blueviolet;
    padding: 10px;
    text-align: center;
    position: absolute;
    top: -20px;
    left: 50%;
    transform: translateX(-50%);
    width: 60%;
}
.chat-inner {
    flex: 1;
    padding: 20px;
    border: 3px solid black;
    margin: 20px;
    display: flex;
    flex-direction: column;
    overflow-y: auto;         
    max-height: 100%;         
}

.message {
    margin-bottom: 10px;
}
.message strong {
    display: block;
}
.message-box {
    border: 2px solid black;
    padding: 10px;
    display: inline-block;
    max-width: 70%;
    background-color: white;
}
.atendente {
    text-align: left;
}
.voce {
    text-align: right;
}
.input-box {
    display: flex;
    border-top: 3px solid black;
    padding: 10px;
    background-color: white;
}
.input-box input {
    flex: 1;
    padding: 10px;
    border: 2px solid black;
}
.input-box button {
    background-color: lightgreen;
    border: 2px solid black;
    padding: 10px;
    cursor: pointer;
    margin-left: 10px;
}

Module.ts (imports)

import { FormsModule } from '@angular/forms';

@NgModule({
  imports: [
    BrowserModule,
    FormsModule
  ],
  ...
})
export class AppModule {}
