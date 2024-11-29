# <strong>Documentação para os testes de Hardware</strong>

📊 📋 📝 ⭐ ✏️ 🎯 💡 ❗ ✅ ❌ 💻 🌐 🛠️ ⚠️🖼️ 📁 🦅 🐈 🐢 🦄 🚦 🔴 🟡 🟢📌 🔍 🕒 🔑


<details>
  <summary>📌 Ajuda para Preenchimento da Documentação</summary>

**Esta área serve para ajuda e poderá ser removida em documentações futuras** 
  
<details>
  <summary><strong>🖼️ Como Inserir Imagens</strong></summary>

Imagens podem ser adicionadas no Markdown utilizando o formato:

markdown
![Texto alternativo](URL_da_imagem)


**Exemplo:**
markdown
![Gráfico de Resultados](https://example.com/grafico.png)


Resultado:
![Gráfico de exemplo](https://miro.medium.com/v2/resize:fit:1400/1*HPUEfcPiw9JvDf1hAqBNkA.png)

</details>


<details>
  <summary><strong>📊 Como Criar Tabelas</strong></summary>

As tabelas são definidas com o seguinte formato:

markdown
| Cabeçalho 1 | Cabeçalho 2           | Cabeçalho 3           |
|-------------|-----------------------|-----------------------|
| Dado 1      | Dado 2               | Dado 3               |
| Outro dado  | Mais informações aqui | Observações adicionais |


**Exemplo de Resultado:**

| ID    | Resultado do Teste                           | Atendeu aos Requisitos? | Observações                                       |
|-------|----------------------------------------------|--------------------------|--------------------------------------------------|
| UC01  | Comunicação funcional com alcance de 20m     | Sim                      | Sinal instável em ambientes com muitas barreiras. |
| UC02  | Resposta do motor inferior a 80ms            | Sim                      | Precisão adequada em movimentações rápidas.      |

---

</details>

<details>
  <summary><strong>📋 Como Criar Listas Enumeradas</strong></summary>
  
Para criar uma lista ordenada, use números seguidos por um ponto:

markdown
1. Item 1
2. Item 2
3. Item 3


**Resultado:**
1. Item 1
2. Item 2
3. Item 3

---

</details>

<details>
  <summary><strong>📝 Como Criar Listas Não Enumeradas</strong></summary>

Para criar uma lista não ordenada, use - ou * antes do texto:

markdown
- Primeiro item
- Segundo item
- Terceiro item


**Resultado:**
- Primeiro item
- Segundo item
- Terceiro item

</details>
</details>

## **⭐ Descrição**

Descreva brevemente o objetivo do teste neste paragrafo. Seja descritivo com os objetivos específicos.

- UC01 - Use estes paragrafos para explicar os testes realizados em partes. Descreva o primeiro teste e objetivo;
- UC02 - Descreve o segundo teste e obejtivo;
- UC0N - Descreva o enésimo teste e objetivo. 

----


## 🛠️ Como usar

### 📁 Estrutura do Repositório

Explique como o conteúdo está organizado no repositório para facilitar a navegação. Não seja tão descritivo nesse ponto, apenas saliente os principais arquivos que foram utilizados e as suas relações:

**Exemplo:**
/libraries
  /nrf24l01
    - common_radio.h
    - transmitter.cpp
    - transmitter.h
    - receiver.cpp
    - receiver.h
  /dynamixel
    - position_control.cpp
    - position_control.h
/datasheets
  - nrf24l01.pdf
  - as5600.pdf
  - mx28.pdf
/src
  - main.cpp
  - boardConfig.h


--- 

### 🖥️ Dependências  
1. **Ambientes de Programação:**  
   - Liste os ambientes utilizados, como IDEs, ferramentas de desenvolvimento ou sistemas operacionais compatíveis.  
     Exemplo:  
     - **VSCode**: [Link para download](https://code.visualstudio.com/)  
     - **ESP-IDF**: [Guia de instalação](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html)  
2. **Softwares e Licenças:**  
   - **Softwares Utilizados:** Indique os softwares necessários para o projeto.  
     Exemplo:  
     - **Python 3.10+**: [Link para download](https://www.python.org/downloads/)  
     - **CMake**: [Instalação do CMake](https://cmake.org/install/)  
   - **Licenças:** Especifique se algum software exige licenças, como LGPL, MIT, etc.  
3. **Build do Projeto:**  
   - Caso seja necessário compilar, inclua as instruções no formato de spoiler para facilitar a navegação:  
     
markdown
     <details>
       <summary>Como buildar o projeto</summary>
       1. Clone o repositório:
bash
       git clone https://github.com/iOsnaaente/seu-repositorio.git
       cd seu-repositorio
       
2. Configure as dependências usando o seguinte comando:
bash
       ./configure.sh
       
3. Compile o código com:
bash
       make
       
</details>
  
4. **Necessidades para Rodar Exemplos:**  
   - Inclua uma lista clara do que é necessário para executar os exemplos:  
     - **Dependências instaladas:** (como pacotes Python: pip install -r requirements.txt)  
     - **Hardware conectado:** Indique portas e conexões necessárias.  
     - **Configurações iniciais:** Exemplo: "Configure o arquivo config.json com seus dados."  
---


### 🔑 Executando os Testes:  

#### 📋 Rotina dos testes:  

| ID    | Descrição                                                                 | Objetivo do Caso de Uso                                             |
|-------|---------------------------------------------------------------------------|----------------------------------------------------------------------|
| UC01  | **Dispositivo 1:** Avaliação do rádio nRF24L01                            | Verificar se a comunicação via rádio opera com integridade e alcance. |
| UC02  | **Dispositivo 2:** Controle dos motores Dynamixel                         | Avaliar a resposta e a precisão no controle de posição do motor.     |
| UC03  | **Sistema:** Sincronização entre dispositivos conectados ao Modbus TCP/IP | Testar a consistência dos dados enviados e recebidos.                |


#### 📝 UC01: Avaliação do rádio nRF24L01  
**Objetivo:** Avaliar a transmissão e recepção de dados entre dois dispositivos.
- **Equipamentos Necessários:**
  - 2 módulos nRF24L01
  - Fonte de alimentação estável
  - Sistema de monitoramento serial (ex: Arduino ou ESP32)
- **Passos:**
  1. Conecte o módulo nRF24L01 ao microcontrolador de acordo com o esquema elétrico.
  2. Carregue o código de teste no microcontrolador (arquivo: transmitter_test.ino).
  3. Ative o receptor e verifique os pacotes recebidos no monitor serial.
  4. Interrompa a comunicação e avalie o comportamento do sistema ao recuperar o sinal.

Neste tópico, descreva como é possível executar os testes realizados para replicar os resultados descritos acima. 
Liste os principais casos de uso dos itens a serem testados, especificando claramente o objetivo de cada um.


---


## **✅ Conclusão do(s) teste(s)**
Baseado nos objetivos descritos acima, para fins pŕaticos, será apresentado a tabela de conclusão dos testes realizados abaixo.


<details>
  <summary>💡 Ajuda para Preenchimento de Resultados e Documentação</summary>

### **Instruções para Preenchimento de Resultados**

1. Para cada teste realizado, registre os resultados em uma tabela.
2. Se possível, insira imagens ou links para logs e gráficos (ajuda abaixo).
3. Liste os problemas observados e os contextos relevantes.
4. Conclua com o status do teste, avaliando a necessidade de mais avaliações ou se as conclusões obtidas são suficientes. 

</details>

**Resultados obtidos nos testes:**

| ID    | Resultado do Teste                           | Atendeu aos Requisitos? | Observações                                       |
|-------|----------------------------------------------|--------------------------|--------------------------------------------------|
| UC01  | Comunicação funcional com alcance de 20m     | Sim                      | Sinal instável em ambientes com muitas barreiras. |
| UC02  | Resposta do motor inferior a 80ms            | Sim                      | Precisão adequada em movimentações rápidas.      |
| UC0N  | Latência de 45ms entre transmissões Modbus   | Sim                      | Desempenho consistente em ambiente controlado.   |

**Conclusões Detalhadas dos Testes**
Com base nos resultados da tabela acima, descreva em um paragrafo as conclusões detalhadas de cada teste realizado.

- **UC01:** A comunicação alcançou um desempenho funcional com um alcance de até 20 metros. Apesar disso, em ambientes com muitas barreiras, o sinal apresentou instabilidade, indicando a necessidade de ajustes para melhorar a robustez em cenários adversos.  
- **UC02:** O motor apresentou uma resposta inferior a 80ms, atendendo às expectativas de precisão em movimentações rápidas. Isso confirma a adequação do controle implementado para aplicações que exigem alta reatividade.  
- **UC0N:** A latência medida de 45ms entre transmissões Modbus demonstrou consistência em ambientes controlados, garantindo que o sistema opere dentro dos limites aceitáveis para aplicações industriais.  

---

**Necessidade de Novos Testes**

| Teste   | Suficiente? | Novos Testes Necessários                                   | Observações                              |
|---------|-------------|-----------------------------------------------------------|------------------------------------------|
| **UC01** | ✅ Sim       | 🚫 Nenhum                                                 | Melhorias no ambiente podem ser opcionais. |
| **UC02** | ✅ Sim       | 🚫 Nenhum                                                 | O desempenho está dentro do esperado.   |
| **UC0N** | ❓ Parcial   | ✅ Testes em ambientes com ruído ou condições extremas.   | Avaliar impacto de fatores externos.    |

Legenda:  
- ✅ **Sim:** Teste suficiente e não requer mais experimentação.  
- ❓ **Parcial:** Teste suficiente, mas pode haver ganhos com testes adicionais.  
- 🚫 **Nenhum:** Não há necessidade de novos testes.


---


### 🌐 Instruções para Contribuição  
1. Crie um fork do repositório.  
2. Adicione suas alterações seguindo o padrão de documentação.  
3. Execute testes básicos para validar.  
4. Submeta um Pull Request com a descrição detalhada das mudanças.

- Adicionalmente, envie revisões para [iOsnaaente](https://github.com/iOsnaaente).


<p align="center">
  :octocat: Desenvolvedores/Contribuintes :octocat:
</p>

<p align="center">
  Liste o time responsável pelo desenvolvimento do projeto.
</p>

<p align="center">
  <a href="https://github.com/iOsnaaente">
    <img src="https://avatars.githubusercontent.com/u/45924781?v=4" width="115">
    <br><sub>iOsnaente</sub>
  </a>
</p>
