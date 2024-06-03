# quete-d-coupage-ip

### SYMÉTRIQUE:

Dans le cas symétrique, il faut satisfaire le plus pôle demandant le plus grand nombre (ici informatique avec 50 adresses, 2^6= 64 adresses), et appliquer le même découpage pour les autres pôles.

Avec comme masque de sous-réseaux à /26, permettant l’attribution des 64 adresses.

- Pôle informatique: 172.16.1.0/26, soit des adresses allant de 172.16.1.0 à 172.16.1.63

- Pôle développement: 172.16.1.64/26, soit des adresses allant de 172.16.1.64 à 172.16.1.127
- Pôle administratif: 172.16.1.128/26, soit des adresses allant de 172.16.1.128 à 172.16.1.191
- Pôle technicien: 172.16.1.192/26, soit des adresses allant de 172.16.1.192 à 172.16.1.255

### ASYMÉTRIQUE:

Dans le cas asymétrique, on adapte pour chaque pôle le nombre d’adresses disponibles à son nombre d’hôtes.

Calculons donc le nombre d’hôtes grâce au tableau des puissances vu plus haut et leurs CIDR
- Pôle informatique : 50 équipements ⇒ 64 adresses (masque : /26)
- Pôle développement : 12 équipements ⇒ 6 adresses (masque : /28)
- Pôle administratif : 20 équipements ⇒ 32 adresses (masque : /27)
- Pôle technicien : 15 équipements ⇒ 32 adresses (masque : /27)

On a donc comme attribution des adresses:
- Pôle informatique: 172.16.1.0/26, soit des adresses allant de 172.16.1.0 à 172.16.1.63

- Pôle développement: 172.16.1.64/29, soit des adresses allant de 172.16.1.64 à 172.16.1.79
- Pôle administratif: 172.16.1.80/27, soit des adresses allant de 172.16.1.80 à 172.16.1.111 
- Pôle technicien: 172.16.1.112/27, soit des adresses allant de 172.16.1.112 à 172.16.1.143
