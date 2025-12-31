✅ PASSO A PASSO — GERAR CERTIFICADO (TESTE)
✅ Opção 1 — Instalar o OpenSSL no Windows (recomendado)
🔹 1. Baixar o OpenSSL
Acesse um instalador confiável:
👉 https://slproweb.com/products/Win32OpenSSL.html
Escolha:
•	Win64 OpenSSL v3.x.x (se seu Windows for 64 bits)
Baixe a versão:
•	“Win64 OpenSSL v3.x.x Light” (já é suficiente)


📁 1️⃣ Entre na pasta onde os arquivos serão criados
cd C:\Users\Antonio Oliveira\Desktop\Contratos_sistemas\notaFiscal
________________________________________
🔐 2️⃣ Criar a CHAVE PRIVADA (chave.key)
& "C:\Program Files\OpenSSL-Win64\bin\openssl.exe" genrsa -out chave.key 2048
✔️ Cria o arquivo:
chave.key
________________________________________
📜 3️⃣ Criar o CERTIFICADO (certificado.crt)
& "C:\Program Files\OpenSSL-Win64\bin\openssl.exe" req -new -x509 -key chave.key -out certificado.crt -days 365
Quando pedir os dados, pode usar por exemplo:
Country Name (2 letter code): BR
State or Province Name: SP
Locality Name: Sao Paulo
Organization Name: Empresa Teste
Organizational Unit Name: TI
Common Name: teste.local
Email Address: teste@teste.com
✔️ Cria o arquivo:
certificado.crt
________________________________________
📦 4️⃣ Gerar o CERTIFICADO FINAL (certificado.pfx)
& "C:\Program Files\OpenSSL-Win64\bin\openssl.exe" pkcs12 -export -out certificado.pfx -inkey chave.key -in certificado.crt
🔑 Vai pedir:
Enter Export Password:
👉 Guarde essa senha.
✔️ Cria o arquivo:
certificado.pfx
________________________________________
📂 5️⃣ Conferir os arquivos gerados
dir
Resultado esperado:
chave.key
certificado.crt
certificado.pfx
________________________________________
⚠️ ATENÇÃO IMPORTANTE
❌ Esse certificado NÃO serve para NFe real / SEFAZ / Produção
✅ Serve apenas para:
•	Testes
•	Desenvolvimento
•	Aprender OpenSSL
•	Testar código PHP local

