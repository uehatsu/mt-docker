FROM httpd:2.4.41

RUN apt-get update \
 && apt-get upgrade -y \
 && apt-get install -y \
    vim cpanminus make gcc \
    libdbi-perl libclass-dbi-mysql-perl libclass-dbi-pg-perl \
    libyaml-syck-perl libcrypt-ssleay-perl libxmlrpc-lite-perl \
    libgd-perl libarchive-zip-perl perlmagick libcrypt-dsa-perl \
    libipc-run-perl libcgi-psgi-perl libimager-perl \
    libcache-memcached-perl libplack-perl libxml-sax-expat-perl \
    libxml-sax-expatxs-perl \
 && cpanm Cache::File DBD::SQLite DBD::SQLite2 Digest::SHA1 \
    Mozilla::CA XML::LibXML::SAX XMLRPC::Transport::HTTP::Plack \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

#RUN usermod -u 1000 www-data \
# && groupmod -g 1000 www-data \
# && chown -R www-data:www-data /usr/local/apache2/htdocs
