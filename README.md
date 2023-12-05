Escolhi fazer esse sistema de login seguro independente em Django justamente para testar as opções disponíveis para login com 2 fatores, sem utilizar provedores de identidade de terceiros, 
como GitHub, Google, Azure, Auth0, LikedIn, entre outros. Para o sistema de autenticação usando provedores de terceiro, como o Google, por exemplo, usaria o Allauth em Django, que inclui a 
autenticação através de vários provedores.

![autenticacao_2fa](https://github.com/JulioDEVReis/2FA-Login-Page-Django/assets/142347463/b4f4177e-d211-47a1-b82b-6b392910c88e)

A proposta era usar uma biblioteca que menos impactasse no meu código e que eu pudesse fazer o processo rapidamente, sem impactar também em tempo, a qual dedicaria ao código do aplicativo em si.

Usei então o KAGI, uma vez que a biblioteca requer poucas inclusões em meu código, deixando-o mais limpo para a execução do código do aplicativo que iremos desenvolver, além de usar menos tempo de codigo e configuração na autenticação 2FA, deixando mais tempo livre para usarmos em nosso código do aplicativo a qual a autenticação oferecerá a segurança.

Criei um sistema rápido, sem me importar com estilização, somente para testar a ferramenta, que apresenta o QRCODE para autenticar em 2 fatores com o aplicativo de autenticação no celular.

O resultado é fantastico e rápido.

Apenas precisei editar o settings.py e urls.py para que a biblioteca funcione adequadamente, e importei a pasta templates, do ambiente virtual KAGI para minha pasta Templates do projeto, para justamente fazer possiveis alterações, como por exemplo, colocar tudo em Português e estilizar a pagina.

### Dificuldades e Soluções:

Testei várias opções de bibliotecas e módulos para ver quais necessitavam de menos intervenção em nosso código, para deixar o código mais limpo para a aplicação em si a qual a autenticação irá garantir a segurança.

Caso realmente eu não use um provedor de identidade, como o Google por exemplo, a biblioteca escolhida foi a KAGI, que eu usei nesse projeto. Testei:
- Twilio, para um sistema de autenticação com envio de codigo por SMS, mas que, além de ser pago, só oferecia a autenticação por SMS, podendo ser usado juntamente com o próximo que testei, por exemplo. 
- PYOTP, muito simples e leve, mas que precisa ser totalmente feito para que cumpra sua função, e isso pode levar muito tempo para codar, uma vez que devemos abordar todos os aspectos de segurança necessários.
- django-two-factor-auth, que usa a biblioteca Django-otp, Inspirado pela experiencia de usuario da autenticação em 2 passos do Google, permitindo usuarios autenticarem atraves de chamada, SMS ou usando um aplicativo de autenticação. Gostei muito dessa biblioteca, mas gastei mais tempo codando por ela do que com a biblioteca escolhida, a KAGI. Aqui, a biblioteca sugere o Twilio para a autenticação com SMS.

Usei então a biblioteca KAGI, https://kagi.readthedocs.io/en/latest/, que fornece suporte para chaves de segurança WebAuthn / FIDO2 e tokens TOTP em Django.
Para aprender e usar a ferramente precisei acessar o GitHub https://github.com/justinmayer/kagi e ver vários videos youtube em ingles usando a biblioteca para ver todos os passos necessários, básicos, para que pudessemos ter a funcionalidade da autenticação dupla em funcionamento.

### Tecnologias que utilizei:
- Django (Framework escolhido para a aplicação web, por ser mais robusta e usual)
- Kagi (Sistema de autenticação em 2 fatores)
