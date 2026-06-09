# GitHub Codespaces — Resumo para Certificação GitHub Foundations

O **GitHub Codespaces** é um ambiente de desenvolvimento completo baseado na nuvem. Ele elimina a necessidade de configurar o computador local (instalar runtimes, bancos de dados, extensões, etc.) para rodar um projeto. Ao abrir um Codespace, o GitHub provisiona uma máquina virtual dedicada (utilizando containers Docker) com o ambiente pronto para codificar.

---

## 📌 Os 4 Conceitos-Chave para a Prova

### 1. O arquivo de configuração (`devcontainer.json`)
A prova costuma perguntar como o Codespaces sabe quais ferramentas e configurações devem ser instaladas na máquina virtual.
* **Localização:** Fica guardado dentro da pasta `.devcontainer/` na raiz do repositório.
* **Função:** É um arquivo estruturado em JSON onde você define quais extensões do VS Code serão pré-instaladas, quais portas de rede serão expostas (como a porta de um servidor local) e quais runtimes/ferramentas (Node.js, Python, PL/SQL, etc.) o ambiente terá.

### 2. Interfaces de Uso
O desenvolvedor pode interagir com o ambiente de duas formas:
* **No Navegador:** Uma versão web completa do VS Code roda direto na aba do browser.
* **Na IDE Local:** É possível conectar o VS Code ou o JetBrains instalados no seu computador físico ao Codespace. O processamento e a execução continuam acontecendo na nuvem, mas você usa a sua interface local.

### 3. Diferença Crucial: `github.dev` vs `Codespaces`
Este é um dos pontos de pegadinha mais comuns no exame:

| Recurso | `github.dev` (Editor Web Rápido) | **GitHub Codespaces** |
| :--- | :--- | :--- |
| **Como acessar** | Pressionando a tecla `.` (ponto) no repositório. | Clicando no botão "Code" -> aba "Codespaces". |
| **O que ele é** | Apenas um editor visual leve que roda no browser. | Uma **máquina virtual completa** rodando na nuvem. |
| **Poder de execução** | **Não possui** terminal, não roda código, não roda testes. | **Possui terminal completo**, compila código, executa testes e servidores. |
| **Custo** | 100% gratuito para qualquer repositório. | Possui uma franquia gratuita de horas (o uso excedente é tarifado). |

### 4. Ciclo de Vida e Uso Prático
* **Persistência:** Se você fechar a aba do navegador, o Codespace entra em estado de *Timeout* (pausa) para economizar créditos, mas as suas alterações não commitadas continuam salvas na nuvem. Você pode reiniciar o ambiente a qualquer momento.
* **Múltiplos Ambientes:** Um desenvolvedor pode criar mais de um Codespace para o mesmo repositório (ex: um para corrigir um bug rápido na branch `main` e outro para trabalhar em uma funcionalidade longa em outra branch).

---

> 💡 **Foco para o Exame:** O objetivo principal do Codespaces é resolver o problema do *"na minha máquina funciona"*, trazendo **padronização** para o time de desenvolvimento por meio do arquivo `devcontainer.json`.
