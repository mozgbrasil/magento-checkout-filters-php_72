[checkmark]: https://raw.githubusercontent.com/mozgbrasil/mozgbrasil.github.io/master/assets/images/logos/logo_32_32.png "MOZG"
![valid XHTML][checkmark]

[artigo-composer]: http://mozg.com.br/ubuntu/composer
[ioncube-loader]: http://www.ioncube.com/loaders.php
[acordo]: http://mozg.com.br/acordo-licenca-usuario-final/

# Mozg\CheckoutFilters

--

Filtros

--

Filtre seus métodos de pagamento e envio.

Pagamento
-------

- Filtrar por grupo de clientes
- Filtrar por idade do cliente
- Ocultar outros métodos de pagamento se o total geral for zero

Envio
-------

- Filtrar por grupo de clientes

--

Restrições

--

Restrinja salvar o endereço de faturamento caso a data de nascimento fornecida seja inferior a 18 anos.

--

Restrinja a exibição do método de entrega caso o serviço do Correios esteja on-line

--

## Testando na Heroku

Gostaria de apresentar o aplicativo que disponibilizei para a plataforma Heroku

Com apenas 1 clique, o aplicativo cria sua loja virtual usando a plataforma de comércio eletrônico Magento e instala os módulos da MOZG

[https://github.com/mozgbrasil/heroku-magento#descrição](https://github.com/mozgbrasil/heroku-magento#descrição)

## Instalação - Atualização - Desinstalação - Desativação

--

Sugiro "printar" as telas com todos os procedimentos executados

Envie para nós as imagens das telas na eventualidade de quaisquer dificuldades

--

Este módulo destina-se a ser instalado usando o [Composer][getcomposer]

Execute o seguinte comando no terminal, para visualizar a existencia do Composer e sua versão

	composer --version

Caso não tenha o Composer em seu ambiente, sugiro ler o seguinte artigo [Clique aqui][artigo-composer]

--

É necessário que o servidor tenha o suporte a extensão [ionCube PHP Loader][ioncube-loader]

Para visualizar a existência da extensão nesse ambiente denominado PHP CLI, execute o seguinte comando no terminal

	php -v

Para visualizar se essa extensão está ativa em seu servidor no ambiente denominado PHP WEB

Certique se da presença do arquivo phpinfo.php na raiz do seu projeto

	<?php phpinfo(); ?>

Caso não exista o arquivo phpinfo.php na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

Acesse o arquivo pelo browser

Em seguida pesquise pelo termo "ionCube PHP Loader"

Caso o seu servidor não tenha o suporte a extensão, entre em contato com sua empresa de hospedagem e peça para que eles ativem a extensão

Caso tenha a permissão e queira ativar a extensão, [Clique aqui][ioncube-loader]

Em "Loader Downloads API", efetue download do pacote compatível com o seu servidor

Descompacte o pacote e faça upload do arquivo "loader-wizard.php" para seu servidor, onde será demonstrado o passo a passo para a ativação da extensão

[Clique aqui](https://youtu.be/GZ2J6MLkko4) para ver os processos executados

--

Na presença do "ionCube PHP Loader" efetue o download do seguinte arquivo e coloque na raiz do seu servidor e acesse, se funcionar quer dizer que o "ionCube" está lendo esse tipo de encriptação

https://raw.githubusercontent.com/mozgbrasil/heroku-magento/master/phpinfo-ioncube-encoder10-x86-64-php_72.php

--

Para utilizar o(s) módulo(s) da MOZG é necessário aceitar o [Acordo de licença do usuário final][acordo]

--

Sugiro manter um ambiente de testes para efeito de testes e somente após os devidos testes aplicar os devidos procedimento no ambiente de produção

--

Sugiro efetuar backup da plataforma Magento e do banco de dados

--

Antes de efetuar qualquer atualização no Magento sempre mantenha o Compiler e o Cache desativado

--

Certique se da presença do arquivo composer.json na raiz do seu projeto Magento e que o mesmo tenha os parâmetros semelhantes ao modelo JSON abaixo

	{
	  "minimum-stability": "dev",
	  "prefer-stable": true,
	  "license": [
	    "proprietary"
	  ],
	  "repositories": [
	    {
	      "type": "composer",
	      "url": "https://packages.firegento.com"
	    }
	  ],
	  "extra": {
	    "magento-root-dir": "./",
	    "magento-deploystrategy": "copy",
	    "magento-force": true
	  }
	}

Caso não exista o arquivo composer.json na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

### Para instalar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer require mozgbrasil/magento-checkout-filters-php_72:dev-master

Você pode verificar se o módulo está instalado, indo ao backend em:

	STORES -> Configuration -> ADVANCED/Advanced -> Disable Modules Output

--

### Para atualizar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

Antes de efetuar qualquer processo que envolva atualização no Magento é recomendado manter o Compiler e Cache desativado

	composer update

Na ocorrência de erro, renomeie a pasta /vendor/mozgbrasil e execute novamente

Para checar a data do módulo execute o seguinte comando

	grep -ri --include=*.json 'time": "' ./vendor/mozgbrasil

--

### Para [desinstalar][uninstall-mods] o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer remove mozgbrasil/magento-checkout-filters-php_72

--

### Para desativar o módulo

1. Antes de efetuar qualquer processo que envolva atualização sobre o Magento é necessário manter o Compiler e Cache desativado

2. Caso queira desativar os módulos da MOZG renomeie a seguinte pasta app/code/local/Mozg

A desativação do módulo pode ser usado para detectar se determinada ocorrência tem relação com o módulo

## Como configurar o método

Antes de configurar o módulo você deve cadastrar o CEP de origem, indo ao backend em:

	STORES -> Configuration -> Sales/Shipping Settings -> Origin

Para configurar o método de entrega, acesse no backend em:

	STORES -> Configuration -> Mozg -> Checkout Filters

Você terá os campos a seguir

### • **Ocultar método de pagamento para total zero**

Para "ativar" ou "desativar" o uso do método

### • **Ativar**

Para "ativar" ou "desativar" o uso do método


## Perguntas mais frequentes "FAQ"

### Sobre a restrição de exibição do método

Para o método "mozg_correios" é feito requisição onde caso o serviço esteja offline o método não deve ser exibido

É possível definir para os metodos serem exibido somente caso o Correios esteja offline

## Contribuintes

Equipe Mozg

## License

[Comercial License](LICENSE.txt)

## Badges

[![Join the chat at https://gitter.im/mozgbrasil](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/mozgbrasil/)
[![Latest Stable Version](https://poser.pugx.org/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72/v/stable)](https://packagist.org/packages/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72)
[![Total Downloads](https://poser.pugx.org/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72/downloads)](https://packagist.org/packages/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72)
[![Latest Unstable Version](https://poser.pugx.org/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72/v/unstable)](https://packagist.org/packages/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72)
[![License](https://poser.pugx.org/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72/license)](https://packagist.org/packages/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72)
[![Monthly Downloads](https://poser.pugx.org/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72/d/monthly)](https://packagist.org/packages/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72)
[![Daily Downloads](https://poser.pugx.org/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72/d/daily)](https://packagist.org/packages/mozgbrasil/mozgbrasil/magento-checkout-filters-php_72)
[![Reference Status](https://www.versioneye.com/php/mozgbrasil:mozgbrasil/magento-checkout-filters-php_72/reference_badge.svg?style=flat-square)](https://www.versioneye.com/php/mozgbrasil:mozgbrasil/magento-checkout-filters-php_72/references)
[![Dependency Status](https://www.versioneye.com/php/mozgbrasil:mozgbrasil/magento-checkout-filters-php_72/1.0.0/badge?style=flat-square)](https://www.versioneye.com/php/mozgbrasil:mozgbrasil/magento-checkout-filters-php_72/1.0.0)

:cat2:
