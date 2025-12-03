# Exemplo de Interacao API

Aplicativo Flutter para exemplificar uma interação com uma API. Vamos usar a nova API do Brise II como exemplo.

## Pré-requisitos

- Flutter SDK instalado e configurado (`flutter doctor`).
- Android Studio (SDK/Emulador) ou Xcode (para iOS), conforme plataforma.

## Setup do projeto

Como a CLI do Flutter pode não estar disponível no ambiente atual, o repositório já contém `pubspec.yaml` e `lib/main.dart`. Após instalar o Flutter na sua máquina:

1. No diretório do projeto, gere as pastas de plataforma:
   - `flutter create .`
2. Instale as dependências:
   - `flutter pub get`

---

## Configuração do Dispositivo Android para Debug
Para rodar o aplicativo diretamente no seu celular ou tablet Android, siga estes passos:

### 1. Ativar o Modo Desenvolvedor
Esta etapa só precisa ser feita uma vez por dispositivo:
* Vá em **Configurações** do seu dispositivo.
* Procure por **"Sobre o Telefone"** ou **"Sobre o Dispositivo"**.
* Encontre **"Número da Versão"** (ou **Build Number**).
* **Toque no "Número da Versão" 7 vezes seguidas** até aparecer a mensagem "Você agora é um desenvolvedor!".

### 2. Ativar a Depuração USB (USB Debugging)
* Volte para as **Configurações**.
* Procure por **"Sistema"** e depois **"Opções do Desenvolvedor"**.
* **Habilite a opção "Depuração USB"**
* **Habilite a opção "Depuração Wi-Fi"** (está disponível a partir do **Android 11** e requer que o computador e o celular estejam conectados à **mesma rede Wi-Fi**)

### 3.1. Conectar e Autorizar (USB)
* Conecte o dispositivo ao seu computador usando um cabo USB.
* O dispositivo deve solicitar a **"Permissão para depuração USB"**. **Aceite** e, se disponível, marque a opção **"Sempre permitir a partir deste computador"**.

### 3.2. Conectar e Autorizar (Wi-Fi)
#### **Pareamento:**
    * Dentro da opção "Depuração por Wi-Fi", toque em **"Parear dispositivo com código de pareamento"**. Uma tela aparecerá com um código e um endereço IP/Porta.
#### **Executar o Comando ADB no Computador:**
    * Abra o terminal no seu computador (na pasta do projeto ou em qualquer lugar com o ADB disponível).
    * Execute o comando de conexão/pareamento, substituindo o IP e o código pelos valores exibidos no seu celular:

    ```bash
    # Exemplo de comando no terminal do computador:
    adb pair <IP_DO_CELULAR>:<PORTA>
    # Ex: adb pair 192.168.1.100:4444
    ```

    * Quando solicitado, **insira o código de pareamento** que está sendo exibido no seu celular.
#### **Conectar e Usar:**
    * O dispositivo aparecerá na lista de dispositivos conectados e você poderá rodar o `flutter run` normalmente.

> **Nota:** Se você desconectar e reconectar à rede Wi-Fi, pode ser necessário rodar o comando `flutter run` ou um comando `adb connect` para restabelecer a comunicação sem o cabo.

## Compilando e Executando o Projeto
Após o setup do projeto e a configuração de um dispositivo (USB ou Wi-Fi), você pode executar o aplicativo:

### 1. Verificar Dispositivos Conectados
Abra o terminal na pasta raiz do projeto e execute:

Executar em Modo Debug:
```bash
flutter run
```