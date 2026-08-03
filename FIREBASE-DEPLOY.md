Deploy das regras do Firestore (instruções)

Opção A — Console (rápido; sem instalar nada):
1. Abra https://console.firebase.google.com/project/bem-estar-da-rosina/firestore/rules
2. Substitua o conteúdo pelo arquivo `firestore.rules` deste repositório.
3. Clique em "Publicar".

Opção B — CLI (recomendado para automação):
1. (Se necessário) instale Node.js e então: npm install -g firebase-tools
2. Gere token: firebase login:ci (siga o fluxo no navegador)
3. No repositório, rode:
   firebase use --add bem-estar-da-rosina
   firebase deploy --only firestore:rules --project bem-estar-da-rosina --token "<SEU_TOKEN>"

Testes/recomendações:
- No Console → Firestore → Rules, use "Simular" para testar cenários.
- Se precisar que eu rode o deploy aqui, cole o token gerado por `firebase login:ci` (use com cuidado).