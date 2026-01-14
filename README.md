# TP_Firebase_ReactNativeCLI

## Descrição

Este projeto é um template **React Native CLI** com configuração inicial para integração com **Firebase**.

> Observação: um projeto CLI é diferente de um projeto **Expo Managed**.
> CLI é recomendado para projetos **mais complexos ou que irão crescer**, enquanto Expo é indicado para **projetos pequenos, rápidos e de estudo**.

---

## Pré-requisitos

1. **Node.js**

   * Recomenda-se **Node 20 LTS**:

   ```bash
   nvm install 20
   nvm use 20
   ```
2. **Java JDK** (versão 11 ou superior)
3. **Android Studio** (para emulação Android)
4. **Xcode** (somente macOS, caso queira emular iOS)
5. **Git** (para versionamento)

---

## Passo 1 – Criar projeto CLI

1. Abra o terminal na pasta onde deseja criar o projeto.
2. Execute:

   ```bash
   npx @react-native-community/cli init TP_Firebase_ReactNativeCLI
   ```
3. Aguarde a criação da estrutura completa do projeto:

```
TP_Firebase_ReactNativeCLI/
├─ android/
├─ ios/
├─ App.js
├─ package.json
├─ node_modules/
└─ ...
```

4. Inicialize o repositório Git e envie para o GitHub:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <URL_DO_REPOSITORIO>
git push -u origin main
```

---


## Observações Importantes

1. CLI **permite acesso total às pastas Android e iOS**, facilitando personalizações e builds complexos, diferente do Expo.
2. Para projetos grandes e que precisam de integração nativa com Firebase, CLI é a melhor escolha.
3. Este README serve como base para criar templates de Firebase que podem ser reaproveitados em futuros projetos.
4. Se for usar Expo, o passo de configuração Firebase muda, e muitas personalizações do Android/iOS podem não ser possíveis.

---

# 🔹 PASSO 2 — Criar o projeto no Firebase Console

👉 **Objetivo deste passo:**
Criar um projeto Firebase **do zero**, limpo, que será a base do seu **template de autenticação**.

Nada de código ainda.
Nada de React ainda.
Só Firebase.

---

## 1️⃣ Acessar o Firebase Console

Entre no site oficial:

👉 **[https://console.firebase.google.com](https://console.firebase.google.com)**

> Use a **conta Google que você quer usar profissionalmente**

---

## 2️⃣ Criar um novo projeto

Clique em:

> **“Criar um novo projeto do Firebase”**

---

## 3️⃣ Nome do projeto (muito importante)

Aqui entra uma decisão de arquitetura.

### ✅ Sugestão de nome (template):


> **firebase-auth-template**

Clique em **Continuar**.

---

## 4️⃣ Google Analytics (decisão consciente)

O Firebase vai perguntar:

> **Ativar o Google Analytics para este projeto?**

### 👉 Para TEMPLATE:

✅ **Pode desativar**

Motivo:

* Não é foco agora
* Menos ruído
* Menos configuração

Você pode ativar depois se quiser.

Clique em **Continuar** (ou Criar projeto).

---

## 5️⃣ Criar projeto

O Firebase vai:

* Provisionar serviços
* Criar o projeto na cloud

Espere finalizar.

Quando aparecer:

> **“Seu projeto está pronto”**

Clique em **Continuar**.

---

## 🧠 Conceito importante (fixa isso)

👉 **1 projeto Firebase = 1 backend completo**

Dentro dele você terá:

* Auth
* Banco
* Storage
* Regras
* Providers (Email, Google, etc.)

Seu app React Native **só consome isso**.

---

## 🔴 Fim PASSO 2


---


# 🔹 PASSO 3 — Criar o APP no Firebase (base técnica)

👉 **Objetivo deste passo:**
Registrar o **app React Native CLI** no Firebase para que ele possa:

* Usar **Authentication**
* Usar **Firestore**
* Usar **Storage**

⚠️ Importante:
Aqui **não estamos criando login ainda**, apenas **registrando o app** no Firebase.
Isso é equivalente a “dar identidade” ao app dentro do projeto Firebase.

---

## 3️⃣.1 — Acessar configuração do projeto

1. Acesse:
   👉 [https://console.firebase.google.com](https://console.firebase.google.com)
2. Entre no projeto recém-criado.
3. No menu lateral esquerdo, clique em **Visão geral do projeto**.
4. Clique no **ícone de engrenagem ⚙️**
5. Selecione **Configurações do projeto**.

---

## 3️⃣.2 — Escolher a plataforma correta

Na parte inferior da página você verá três ícones:

* 🌐 Web (`</>`)
* 🤖 **Android**
* 🍎 iOS

### 👉 Para React Native (CLI ou Expo):

✅ **Começamos pelo ANDROID**

**Por quê?**

* Não exige macOS
* É mais simples de configurar
* SHA-1 (Google Auth) entra primeiro aqui

👉 Clique no ícone **Android 🤖**

---

## 3️⃣.3 — Preencher dados do App Android

### 🔹 Nome do pacote (Application ID)

Este campo é **obrigatório**.

📌 Padrão oficial Android:

```txt
com.seudominio.nomeapp
```

### ✅ Sugestão para TEMPLATE:

```txt
com.seuNome.nomeProjeto
```

Exemplo real:

```txt
com.crenildo.tpfirebasecli
```

⚠️ **Muito importante**:

* Esse valor **precisa bater com o app React Native depois**
* Em projetos reais, mudar isso depois é chato
* Para **template**, está tudo bem usar algo genérico

👉 Preencha:

* **Application ID** → obrigatório
* **Nome do app** → opcional

---

## 3️⃣.4 — Baixar google-services.json

Após preencher os dados:

1. Clique em **Registrar app**
2. O Firebase vai gerar o arquivo:

```txt
google-services.json
```

📌 Esse arquivo:

* Identifica seu app no Firebase
* Contém **chaves públicas**
* **Não é segredo**, mas **não deve ser versionado** em projetos reais

👉 **Baixe o arquivo**
👉 **Guarde**, ainda **NÃO vamos colocar no projeto**

---

Perfeito 👍
Vamos **continuar exatamente do ponto em que paramos**, mantendo o tom didático e o formato de README / guia acadêmico.

Vou **dar sequência lógica**, sem pular nada e sem misturar Expo com CLI.

---

# 🔹 PASSO 3 — Criar o APP no Firebase (base técnica)

👉 **Objetivo deste passo:**
Registrar o **app React Native CLI** no Firebase para que ele possa:

* Usar **Authentication**
* Usar **Firestore**
* Usar **Storage**

⚠️ Importante:
Aqui **não estamos criando login ainda**, apenas **registrando o app** no Firebase.
Isso é equivalente a “dar identidade” ao app dentro do projeto Firebase.

---

## 3️⃣.1 — Acessar configuração do projeto

1. Acesse:
   👉 [https://console.firebase.google.com](https://console.firebase.google.com)
2. Entre no projeto recém-criado.
3. No menu lateral esquerdo, clique em **Visão geral do projeto**.
4. Clique no **ícone de engrenagem ⚙️**
5. Selecione **Configurações do projeto**.

---

## 3️⃣.2 — Escolher a plataforma correta

Na parte inferior da página você verá três ícones:

* 🌐 Web (`</>`)
* 🤖 **Android**
* 🍎 iOS

### 👉 Para React Native (CLI ou Expo):

✅ **Começamos pelo ANDROID**

**Por quê?**

* Não exige macOS
* É mais simples de configurar
* SHA-1 (Google Auth) entra primeiro aqui

👉 Clique no ícone **Android 🤖**

---

## 3️⃣.3 — Preencher dados do App Android

### 🔹 Nome do pacote (Application ID)

Este campo é **obrigatório**.

📌 Padrão oficial Android:

```txt
com.seudominio.nomeapp
```

### ✅ Sugestão para TEMPLATE:

```txt
com.seuNome.nomeProjeto
```

Exemplo real:

```txt
com.crenildo.tpfirebasecli
```

⚠️ **Muito importante**:

* Esse valor **precisa bater com o app React Native depois**
* Em projetos reais, mudar isso depois é chato
* Para **template**, está tudo bem usar algo genérico

👉 Preencha:

* **Application ID** → obrigatório
* **Nome do app** → opcional

---

## 3️⃣.4 — Baixar google-services.json

Após preencher os dados:

1. Clique em **Registrar app**
2. O Firebase vai gerar o arquivo:

```txt
google-services.json
```

📌 Esse arquivo:

* Identifica seu app no Firebase
* Contém **chaves públicas**
* **Não é segredo**, mas **não deve ser versionado** em projetos reais

👉 **Baixe o arquivo**
👉 **Guarde**, ainda **NÃO vamos colocar no projeto**


---


## 3️⃣.5 — Adicionar o SDK do Firebase ao projeto React Native CLI (Android)

👉 **Objetivo deste passo:**
Conectar o **projeto Android local** ao Firebase usando o SDK oficial.

📌 Pré-requisitos:

* Projeto React Native CLI criado com sucesso
* Pasta `android/` existente
* Arquivo `google-services.json` já baixado

---

### 3️⃣.5.1 — Escolher o tipo de Gradle

O Firebase oferece duas opções:

* **DSL Kotlin** → `build.gradle.kts`
* **Groovy** → `build.gradle`

### ✅ Qual usar?

👉 **Use GROOVY (`build.gradle`)**

📌 Motivo:

* React Native CLI usa **Groovy por padrão**
* Kotlin DSL é mais comum em projetos Android nativos modernos
* Evita conflito e complexidade desnecessária

---

### 3️⃣.5.2 — Colocar o google-services.json no lugar correto

Copie o arquivo baixado para:

```
android/app/google-services.json
```

📌 Caminho final:

```
TPFirebaseCLI/
└── android/
    └── app/
        └── google-services.json
```

⚠️ Importante:

* O nome do arquivo deve ser **exatamente** `google-services.json`
* Não renomeie

---

### 3️⃣.5.3 — Configurar o Gradle (nível de projeto)

Abra o arquivo:

```
android/build.gradle
```

Adicione **dentro do bloco `buildscript`**:

```gradle
buildscript {
    dependencies {
        classpath 'com.google.gms:google-services:4.4.4'
    }
}
```

📌 Não remova nada existente, apenas **adicione**.

---

### 3️⃣.5.4 — Configurar o Gradle (nível do app)

Abra o arquivo:

```
android/app/build.gradle
```

No final do arquivo, adicione:

```gradle
apply plugin: 'com.google.gms.google-services'
```

📌 Esse plugin é o que:

* Lê o `google-services.json`
* Conecta o app ao Firebase automaticamente

---

### 3️⃣.5.5 — Sincronizar e validar

Agora execute:

```bash
cd android
./gradlew clean
cd ..
npx react-native run-android
```

Se tudo estiver correto:

* O app sobe normalmente
* Nenhum erro de Firebase aparece
* Mesmo sem usar Auth ainda

---

## ✅ Resultado do PASSO 3.5 (corrigido)

✔ Projeto CLI já existente
✔ Firebase conectado ao Android
✔ google-services.json aplicado
✔ Gradle configurado corretamente

👉 **Ainda não usamos Auth, Firestore ou Storage**
👉 Apenas base técnica pronta (como deve ser)

---

## 📌 Próximo passo lógico

### 🔹 PASSO 4 — Instalar Firebase JS SDK (lado JavaScript)

Agora sim vamos:

* Instalar `firebase`
* Criar `services/firebase.js`
* Inicializar:

  * Auth
  * Firestore
  * Storage
* Sem login ainda

Se quiser, eu já escrevo o **PASSO 4 completo** no mesmo padrão de README.

