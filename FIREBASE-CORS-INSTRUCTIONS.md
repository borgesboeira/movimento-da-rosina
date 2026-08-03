Configurar CORS no Firebase Storage (necessário para uploads do site)

1) Arquivo de exemplo (já incluído em firebase/cors.json neste repositório):

[
  {
    "origin": ["https://borgesboeira.github.io"],
    "method": ["GET", "POST", "PUT", "DELETE", "HEAD"],
    "responseHeader": ["Content-Type", "x-goog-resumable", "x-firebase-storage-version"],
    "maxAgeSeconds": 3600
  }
]

2) Aplicar no bucket (duas opções)

# Usando gsutil (mais comum):
#  - instale o Cloud SDK e autentique (gcloud auth login)
#  - depois rode:
gsutil cors set firebase/cors.json gs://bem-estar-da-rosina.firebasestorage.app

# Ou usando gcloud storage (novas versões):
gcloud storage buckets update gs://bem-estar-da-rosina.firebasestorage.app --cors-file=firebase/cors.json

3) Observações
- A alteração de CORS pode demorar alguns segundos para propagar. Teste do navegador limpando cache ou usando um perfil anônimo.
- Se não quiser executar, posso rodar o comando para você — para isso preciso de um Service Account JSON com permissões de Storage Admin ou um token com permissões (p.ex. via Cloud Shell). Forneça o arquivo/token com cuidado; não compartilhe em público.
