# 🕵️‍♂️ AlibiRepo: O Backend do AlibiApp

Bem-vindo ao **AlibiRepo**, o repositório oficial que atua como banco de dados serverless e sistema de moderação para o **AlibiApp** (Marketplace de Álibis).

Este projeto utiliza uma arquitetura baseada em Git para armazenar, gerenciar e distribuir os anúncios do aplicativo de forma totalmente gratuita e descentralizada, eliminando a necessidade de um banco de dados tradicional.

---

## ⚙️ Como Funciona a Arquitetura?

O AlibiApp consome e envia dados diretamente para este repositório através da API do GitHub:

1. **Leitura (Feed):** O aplicativo consome o arquivo `ads.json` diretamente da branch `main` (ou via GitHub Pages) para exibir os anúncios aprovados aos usuários.
2. **Criação de Anúncios:** Quando um usuário cria um anúncio no app, o sistema realiza um fork deste repositório, insere o novo anúncio no JSON e abre um **Pull Request (PR)** automatizado.
3. **Moderação:** Os administradores deste repositório revisam o PR. Se o conteúdo do anúncio estiver de acordo com as regras, o PR é aprovado (Merge) e o anúncio vai imediatamente para o feed de todos os usuários do app.

---

## 📄 Estrutura de Dados (`ads.json`)

Todos os anúncios são armazenados no arquivo raiz `ads.json`. Cada objeto segue o modelo abaixo:

```json
[
  {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "github_username": "usuario_exemplo",
    "title": "Namorado(a) falso(a) para evento de família",
    "description": "Atuo como acompanhante para jantares e eventos familiares. Discreto, educado e com script combinado previamente.",
    "category": "Presencial",
    "location": "São Paulo, SP",
    "price_range": "R$ 150 - R$ 300",
    "contact_whatsapp": "+5511999999999",
    "contact_telegram": "@usuario_exemplo",
    "availability_hours": "Finais de semana e feriados",
    "avatar_url": "[https://avatars.githubusercontent.com/u/0000000?v=4](https://avatars.githubusercontent.com/u/0000000?v=4)"
  }
]
