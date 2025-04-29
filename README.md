# Hotel Reservation Prediction 🏨

Este projeto tem como objetivo demonstrar o processo completo de **MLOps**, desde o **treinamento** de um modelo de Machine Learning até o **deploy** em ambiente de nuvem (**GCP**), utilizando práticas modernas como **Docker** e **Jenkins**.

## 📚 Sobre o projeto

O desafio consistiu em:

- Treinar um modelo de Machine Learning para **prever se um cliente irá cancelar ou não uma reserva de hotel**.
- Construir a infraestrutura necessária para:
  - **Containerizar** a aplicação utilizando **Docker**.
  - Criar um **pipeline de CI/CD** utilizando **Jenkins**.
  - **Deployar** o modelo na **Google Cloud Platform (GCP)**.
- Criar uma **interface web** para que o usuário possa fazer predições de forma prática.

O foco do projeto foi o **aprendizado prático de MLOps** e o desenvolvimento de habilidades de **deploy de modelos de Machine Learning** em ambiente produtivo.

---

## 🚀 Tecnologias e Ferramentas Utilizadas

- **Python**
- **Docker**
- **Jenkins**
- **Google Cloud Platform (GCP)**
- **Flask** (para construção da API)
- **HTML/CSS** (para a interface web)
- **Git/GitHub**
- **Machine Learning** (Scikit-learn)

---

## 🛠 Estrutura do Projeto

```
├── artifacts/          # Modelos e artefatos gerados
├── config/             # Configurações do projeto
├── custom_jenkins/     # Scripts personalizados para Jenkins
├── notebook/           # Análises exploratórias e notebooks de desenvolvimento
├── pipeline/           # Pipelines de treinamento e deploy
├── src/                # Código fonte do projeto
├── static/             # Arquivos estáticos (CSS, imagens)
├── templates/          # Templates HTML da aplicação
├── utils/              # Funções utilitárias
├── Dockerfile          # Dockerfile para containerização
├── Jenkinsfile         # Jenkinsfile para CI/CD
├── README.md           # Este arquivo
├── application.py      # Código principal da aplicação Flask
├── requirements.txt    # Dependências do projeto
├── setup.py            # Configuração de pacote
```

---

## 🎯 Como Executar o Projeto Localmente

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/MLOPS-COURSE-PROJECT-1.git
cd MLOPS-COURSE-PROJECT-1
```

2. Instale as dependências:

```bash
pip install -r requirements.txt
```

3. Rode a aplicação Flask:

```bash
python application.py
```

4. Acesse a aplicação no navegador:

```
http://localhost:5000/
```

---

## ☁️ Deploy na Nuvem

- A aplicação foi containerizada usando **Docker**.
- O **Jenkins** foi utilizado para orquestrar o **build** e o **deploy** do container na **Google Cloud Platform (GCP)**.
- O pipeline automatizado permite atualizações rápidas e seguras no ambiente de produção.

---

## 📸 Demonstrações

Interface Web para predição:

![image](https://github.com/user-attachments/assets/29b4a3b0-5799-4ecf-9dc0-444188f4e978)

Estrutura do Repositório no GitHub:

![image](https://github.com/user-attachments/assets/ab6727d2-b6be-47ca-b8f8-f78a7f9af83d)

---

## 📈 Resultados

- Conclusão bem-sucedida do deploy do modelo na nuvem.
- Automatização do fluxo de integração e entrega contínua (CI/CD).
- Desenvolvimento prático das habilidades em **MLOps**, **Docker**, **Jenkins** e **deploy em GCP**.

---

## 👨‍💻 Autor

**Eduardo Santos Sousa**

[[LinkedIn](https://www.linkedin.com/in/eduardo-s-sousa/)] | [GitHub](https://github.com/eduardosantossousa)

---
