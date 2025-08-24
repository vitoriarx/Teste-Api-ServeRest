# Testes de API com Postman + Newman + ServeRest

Projeto criado para demonstrar **habilidades práticas em QA** aplicando testes automatizados de API, integração contínua e geração de relatórios.

---

## Tecnologias utilizadas
- **[Postman](https://www.postman.com/)** → Criação e organização das collections de testes  
- **[Newman](https://www.npmjs.com/package/newman)** → Execução automatizada das collections  
- **[newman-reporter-htmlextra](https://www.npmjs.com/package/newman-reporter-htmlextra)** → Relatórios HTML detalhados  
- **[ServeRest](https://serverest.dev/)** → API fake utilizada para simular um backend de e-commerce  
- **[GitHub Actions](https://docs.github.com/pt/actions)** → Pipeline CI/CD configurado para rodar os testes automaticamente  
- **[GitHub Pages](https://pages.github.com/)** → Publicação dos relatórios de forma acessível via web  

---

## Estrutura do projeto

```bash
Teste-Api-ServeRest
┣ 📂 .github/workflows # Pipeline CI/CD (Newman + Deploy)
┣ 📂 postman # Collection de testes (.json)
┣ 📂 reports # Relatórios HTML (não versionados, gerados no CI)
┣ 📜 .gitignore # Ignora arquivos desnecessários
┣ 📜 README.md # Documentação do projeto
```

---

## Como funciona o pipeline
1. **Criação de usuário + Login** → Gera um token dinâmico automaticamente.  
2. **Execução da Collection** → Testes em endpoints de `usuarios` e `produtos`.  
3. **Geração do Relatório** → Produzido em HTML pelo `htmlextra`.  
4. **Publicação Automática** → Deploy direto no **GitHub Pages** após o CI.  

---

## Relatório Online
Acesse o último relatório de execução diretamente aqui:  
**[Relatório Newman - GitHub Pages](https://vitoriarx.github.io/Teste-Api-ServeRest/)**  

---

## Testes implementados
- [x] **Usuário**
  - Criar usuário
  - Login com token JWT
  - Listar usuários
- [x] **Produtos**
  - Cadastrar produto
  - Listar produtos
  - Editar produto
  - Excluir produto

---

## 🧑‍💻 Como executar localmente
1. Clone este repositório:
```bash
   git clone https://github.com/vitori-arx/Teste-Api-ServeRest.git
   cd Teste-Api-ServeRest
```
2. Instale as dependências necessárias:
```bash
    npm install -g newman newman-reporter-htmlextra
```
3. Rode a collection manualmente:
```bash
    newman run ./postman/TesteApiServeRest.postman_collection.json \
    -r htmlextra \
    --reporter-htmlextra-export ./reports/index.html
```
4. Abra o relatório:
```bash
   ./reports/index.html.
```
---
Diferenciais do projeto: 
- Automação completa sem necessidade de intervenção manual
- Relatórios HTML acessíveis online via GitHub Pages
- Pipeline CI/CD com execução automática a cada push
---

## Autora: Vitoria  Melo | Analista de Qualidade de Software
