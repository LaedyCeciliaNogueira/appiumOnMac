## Configurando Appium no MAC
Linguagem de programação: [Java - 8](https://www.oracle.com/br/java/technologies/javase/javase-jdk8-downloads.html)
Framework: [Appium Desktop - 1.17.1](https://github.com/appium/appium-desktop/releases/tag/v1.17.1)
Emulador: [Android SDK - 193.65](https://developer.android.com/studio)
Ambiente de execução: [Node - 12.16.1](https://nodejs.org/en/)


**Instalando Appium:**

> No cmd insira:
> `sudo npm install -g appium --unsafe-perm=true --allow-root` 
> `sudo npm install -g appium-doctor`

![install appium](https://imgur.com/0RpM9iP.png)

![install Appium doctor](https://imgur.com/8GaxqJa.png)
**Configurando o Bash:**

> No cmd insira:
> `touch .bash_profile`
> `open ~/.bash_profile`

![bash configure](https://imgur.com/tyB990i.png)

- Confirmando caminho do android:
 ![confirmando Android](https://imgur.com/YKvcUN8.png)
   
 - Confirmando caminho do java:
> No cmd insira:
> `/usr/libexec/Java_home`
> 
![enter image description here](https://imgur.com/EtbcdCk.png)
 
 - No cmd- bash (exemplo para inserir no bash):

>         export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-9.0.4.jdk/Contents/Home/
>         export PATH=/Library/Java/JavaVirtualMachines/jdk-9.0.4.jdk/Contents/Home/bin:$PATH
>         export ANDROID_HOME=/Users/laedycecilianogueira/Library/Android/sdk
>         export PATH=$PATH:$JAVA_HOME/bin:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools:$ANDROID_HOME/tools/bin

Agora vamos verificar o Appium doctor e ADB:

> Insira o mesmo código do cmd bash acima e depois insira os comandos:
> `appium-doctor --android`
> 
![appium doctor ok](https://imgur.com/lw7oRhF.png)
> `adb`

![adb Ok](https://imgur.com/SBlXDMH.png)

Agora vamos configurar o HOME no Appium:

> Abra o Appium Desktop > `Edit Configurations`
> Insira o `ANDROID_HOME` e `JAVA_HOME`

![config edit configurations](https://imgur.com/ajlPRIv.png)

Agora vamos criar um emulador para testar:

> Abra o Android Studio
> 
> 
>  1. `Start a new Android Studio project`
>  2. `Empty Activity` > `Next`
>  3. Crie um projeto > language: Java > escolha o android
>  4. `AVD Manager`
>  5. `Create virtual device`
>  6. Escolha o android e faça download do android desejado
>  7. Conclua as etapas e aperte Play, o android irá aparecer na sua tela
> 
>

 - Criar novo projeto

![criar android etapa 1](https://imgur.com/FzqsIu7.png)
> 

 - Criar Projeto

![criar android etapa 2](https://imgur.com/qY4YiHN.png)

 - Criar Android

![criar android etapa 3](https://imgur.com/Z7DcZoC.png)

 - Start Android

![start Android](https://imgur.com/1Jzf9PK.png)

> **Mas e se eu quiser usar o Android do smartphone?**
> 
>     1. Torne-se Desenvolvedor em configurações
>     2. Ative a depuração via usb
>     3. Conect o cabo usb
> 
> **Como encontro meu android device?**
> No cmd insira:  `adb devices`
> Lá irá aparecer todos os androids conectados, escolha qual vc quer usar, por exemplo: `emulator-5554` (guarde este dado vamos usar no próximo passo).
![devices](https://imgur.com/PTwJJ1B.png)

Agora vamos configurar o Appium:

> Para isso vamos abrir o Appium desktop escolher a opção: `Start Server`
> Clicar na `lupa` do menu
> Clicar em `Custom Server` do Menu
> Em `Desired Capabilities` vamos inserir as informações, verifique o exemplo abaixo:
> 
>     “platformName”: “Android”,  
>     “deviceName”: “emulator-5554",  
>     “automationName”: “uiautomator2",  
>     “appPackage”: “com.android.calendar",  
>     “appActivity”: “Calendar”

 - Exemplo do meu server:

![meu exemplo server](https://imgur.com/aA8FzTr.png)
Como executou:
![Appium Executado](https://imgur.com/MfTzLrb.png)

   **Observação:** Para usar um dos aplicativos do android temos que instalar o [APK](https://apkpure.com/apk-tool/org.spatialia.tool), para instalar, basta arrastar o arquivo para dentro do smartphone emulador. 
    Para device real, basta baixar pelo google play.

> Prontinho, com tudo configurado, agora é só criar seus projeto no eclipse, IntelliJ, etc. :D
