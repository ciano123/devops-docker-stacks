#################### Versão 1.0 ####################
# Versão HTTPS com Debian 12, PHP 8.4 e dependencias + NodeJS 22
####################################################

# Usa a imagem oficial do Debian/12
FROM debian:12

# Atualiza os pacotes e instala o TZDATA
RUN apt-get update && \
    apt-get install -y \
    apache2 \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg2 \
    lsb-release \
    software-properties-common \
    tzdata \
    unzip \
    vim \
    wget

# Corrige o fuso do container
ENV TZ=America/Fortaleza

# Adiciona o repositório do PHP mantido pelo sury.org
RUN curl -fsSL https://packages.sury.org/php/apt.gpg | gpg --dearmor -o /etc/apt/trusted.gpg.d/php.gpg && \
    echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list

# Instala PHP 8.4 e extensões
RUN apt-get update && apt-get install -y \
    libapache2-mod-php8.4 \
    libcurl4-openssl-dev \
    libfreetype6-dev \
    libjpeg-dev \
    libpng-dev \
    libxml2-dev \
    libzip-dev \
    php8.4 \
    php8.4-bcmath \
    php8.4-cli \
    php8.4-curl \
    php8.4-fpm \
    php8.4-gd \
    php8.4-intl \
    php8.4-mbstring \
    php8.4-mysql \
    php8.4-pgsql \
    php8.4-soap \
    php8.4-sqlite3 \
    php8.4-xml \
    php8.4-zip

# Verifica versão do php instalado
RUN php -v

# Instalação da ferramenta composer - Gerenciador de módulos
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php --install-dir=/usr/local/bin --filename=composer && \
    chmod +x /usr/local/bin/composer && rm composer-setup.php && \
    composer --version

# Instalação do NodeJS 22
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - && \
    apt-get install -y nodejs 

# Confirma a instalação
RUN node -v && npm -v

# Ativando o modulo Rewrite
RUN a2enmod rewrite && \
    a2enmod ssl

# Página principal em branco
RUN echo "Ambiente indefinido" > /var/www/html/index.html

# Adiciona arquivo de configuração do Apache2 para app Laravel
#COPY ./conf-files/laravel-app.prod.conf /etc/apache2/sites-available/laravel-app.conf

# Desabilita site padrão e habilita app laravel
#RUN a2dissite 000-default
#RUN a2ensite laravel-app

# Define o diretório padrão da aplicação
#WORKDIR /var/www/html/app/

# A presença do arquivo 'hot' na pasta 'public/' faz que o Laravel aponte os
# assets front-end para a porta 5137, do servidor de desenvolvimento Vite, em
# vez dos assets buildados, mesmo com as flags APP_ENV=production e
# APP_DEBUG=false presentes no .env.
# Referência: https://stackoverflow.com/a/76652064
# RUN rm ./public/hot

# Adiciona descrição
LABEL org.opencontainers.image.title="PMS PHP Laravel Base"
LABEL org.opencontainers.image.description="Web server base image for Laravel 12 with PHP 8.4, Node.js 22, and Apache on Debian 12."
LABEL org.opencontainers.image.version="1.0"
LABEL org.opencontainers.image.authors="Cassiano Souza & Renan Guedes"
LABEL org.opencontainers.image.licenses="PMS"

# Expõe a porta do container
EXPOSE 80

# Comando principal do container
CMD ["apachectl", "-D", "FOREGROUND"]
