# thunar-shares-plugin
Thunar plugin to quickly share a folder using Samba without requiring root access

http://goodies.xfce.org/projects/thunar-plugins/thunar-shares-plugin

Package compiled and packaged by: Stefano Capitani <stefano@manjaro.org>

Converted and packaged to .deb, "debian_firmware-9.4.0-amd64" by: Elppans Dark Elven <anonymous@anonymous>

Source Code Author of version 0.2.0: Daniel Morales <daniel@daniel.com.uy>

Link of all those responsible: https://git.xfce.org/thunar-plugins/thunar-shares-plugin/

XFCE Link Github: https://git.xfce.org/

Report BUG: https://bugzilla.xfce.org/

XFCE Project: https://xfce.org/

# Sobre thunar-shares-plugin (pt_BR):

Thunar plugin para compartilhar rapidamente uma pasta usando o Samba sem exigir acesso root

http://goodies.xfce.org/projects/thunar-plugins/thunar-shares-plugin

Pacote compilado e embalado por: Stefano Capitani <stefano@manjaro.org>

Convertido e empacotado em .deb, "debian_firmware-9.4.0-amd64" por: Elppans Dark Elven <anonymous@anonymous>

Autor do Código Fonte da versão 0.2.0: Daniel Morales <daniel@daniel.com.uy>

Link de todos os responsáveis: https://git.xfce.org/thunar-plugins/thunar-shares-plugin/

Link Github do XFCE: https://git.xfce.org/

Reportar BUG: https://bugzilla.xfce.org/

Projeto XFCE: https://xfce.org/

Link original: http://mirror.ventraip.net.au/Manjaro/stable/community/x86_64/thunar-shares-plugin-0.2.0.git-5-x86_64.pkg.tar.xz

Description of the Debian "control" package:

pt_BR: Descrição do pacote Debian "control":

Package: thunar-shares-plugin

Priority: optional

Version: 0.2.0.git-5

Architecture: amd64

Maintainer: Stefano Capitani <stefano@manjaro.org>

Depends: thunar, samba

Description: Thunar plugin to quickly share a folder using Samba without requiring root access.
http://goodies.xfce.org/projects/thunar-plugins/thunar-shares-plugin


# Tutorial (em pt_BR):

Para usar, verifique primeiro se seu sistema está configurado. Se não estiver faça as seguintes alterações (como super usuário):

# Samba Share:

sudo mkdir -p /var/lib/samba/usershare

sudo groupadd -r sambashare

sudo chown root:sambashare /var/lib/samba/usershare

sudo chmod 1770 /var/lib/samba/usershare


# Habilite ou adicione no arquivo /etc/samba/smb.conf:

name resolve order = wins lmhosts hosts bcast

usershare path = /var/lib/samba/usershare

usershare max shares = 100

usershare owner only = false

usershare allow guests = yes

force group = sambashare


# Modifique a linha "hosts" em /etc/nsswitch.conf para ficar desta forma:

hosts: files mdns4_minimal [NOTFOUND=return] wins dns mdns4

# Adicionae o seu usuário ao grupo sambashare:

sudo gpasswd sambashare -a $USER

# Instalando o pacote:

wget https://github.com/elppans/thunar-shares-plugin/raw/master/thunar-shares-plugin-0.2.0.git-5_amd64.deb

dpkg -i thunar-shares-plugin-0.2.0.git-5_amd64.deb

# Compartilhando pastas

Após a configuração, para compartilhar basta clicar com o botão direito em qualquer pasta e em "Propriedades > Compartilhar" (como usuário normal)

![alt text](https://i.imgur.com/uagjJW2.png)
