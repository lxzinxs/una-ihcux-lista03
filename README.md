# 🔍 ScannerExpert: Visibilidade de Status e Heurísticas de Nielsen (Lista 03)

Este projeto consiste em um módulo de "Deep Scan" desenvolvido em **C# (.NET)**. O objetivo principal foi aplicar a primeira Heurística de Nielsen: **Visibilidade do Status do Sistema**, garantindo que o usuário saiba exatamente o que está acontecendo em tempo real.

---

## 🚀 O Desafio: "Scanner de Sistema"

Diferente de sistemas que deixam o usuário esperando sem feedback, este algoritmo utiliza técnicas de interface de linha de comando (CLI) para simular um processamento real de hardware.

### Etapas de Desenvolvimento:
1. **Navegação e Estrutura:** Utilização do diretório base `LabDotnet` para centralizar os projetos de laboratório.
2. **Scaffolding:** Criação do projeto via terminal com `dotnet new console -n ScannerExpert`.
3. **Simulação de Feedback:** Implementação de um array de strings para iterar sobre diferentes fases de análise do sistema.
4. **Manipulação de Fluxo:** Uso de `Thread.Sleep` para criar intervalos de espera e o caractere de escape `\r` para atualizar a mesma linha no terminal, simulando dinamismo.

---

## 🛠️ Tecnologias e Conceitos Aplicados

* **Linguagem:** C# (.NET).
* **Thread.Sleep(1500):** Pausa a execução do programa por 1,5 segundos para simular a carga de processamento de hardware.
* **Laço `foreach`:** Utilizado para percorrer a lista de tarefas ("Verificando CPU", "Lendo RAM", etc.).
* **UX/IHC:** Uso de cores (`ConsoleColor`) para diferenciar o status de processamento (Ciano) e sucesso (Verde), facilitando a leitura rápida do usuário.

---

## 💻 Lógica de Visibilidade

O código utiliza o retorno do cursor ao início da linha para atualizar o status sem poluir o terminal:

```csharp
foreach (string fase in fases)
{
    // O \r faz o cursor voltar ao início da linha
    Console.Write($"\r[PROCESSANDO] {fase}   ");
    Thread.Sleep(1500); 
}
```

---

## 📸 Evidências de Execução

Abaixo, os registros que comprovam o sistema informando o status em tempo real:

### 1. Processamento Ativo
Demonstra o sistema durante a fase de sincronização de SDKs:
<img src="./Captura de tela 2026-03-26 201146.png" alt="Sistema Processando" width="100%">

### 2. Análise Concluída
Resultado final após o ciclo de vida do scanner ser completado com sucesso:
<img src="./Captura de tela 2026-03-26 201158.png" alt="Análise Concluída" width="100%">

---
**Desenvolvido por Lucas Nery Miranda** *Estudante de Ciência da Computação - UNA Contagem*
