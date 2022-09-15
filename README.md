## Exercice 1 :

1.	Les commandes tapées par l'utilisateur se trouve dans les dossiers bin et sbin.

2.	C'est la variable d'environnement $HOME qui permet a cd sans paramètre de retourner à l'environnement personnel

3.	La variable d'environnement LANG détermine la langue utiliser par les logiciels, PWD permet de savoir dans quel repertoire on se trouve, OLDPWD permet de trouver celui ou on était juste avant et SHELL nous donne l'interpreteur de commande utilisé.

4. On utilise la commande ```my_var='test'```, et ```echo $my_var```

5.	La variable n’existe plus car c’est une variable locale et que l’on a changé de niveau, exit permet de retourner au précédent 

6.	 La variable d’environnement pourra être retrouver de partout

7.	On utilise ‘export NOM= « Thomas Jakubowski » ; echo $NOM ;
8.	On utilise ‘echo Bonjour a vous, $NOM !’ pour écrire une phrase suivi d’une variable
9.	Unset va supprimer la variable, elle n’existera plus, en mettant une valeur vide la variable existera.
10.	IL faut utilisé ‘echo ‘$Home = chemin’’, on utilise ‘ pour mettre des nom de variable sans afficher son contenu


## Exercice 2 :

```#!/bin/bash
echo "Entrer un mot de passe !"
mdp="aze+123"
read inputMdp
if [ "$inputMdp" = "$mdp" ]; then
  echo "Le mot de passe est juste !"
else
  echo "Le mot de passe est faux !"
fi```

## Exercice 3 :

```#!/bin/bash
function is_number()
{
re='^[+-]?[0-9]+([.][0-9]+)?$'
if ! [[ $1 =~ $re ]] ; then
return 1
else
return 0
fi
}

is_number $1
if [ $? -eq 0 ]; then
  echo "C'est un nombre!"
else 
  echo "Ce n'est pas un nombre !"
fi```

## Exercice 4 :

```#!/bin/bash
read user
if [ "_user" = _$USER" ]; then
  echo "L'utilisateur est correct"
elif [ "_$user" = "_" ]; then
  echo "Utilisation: $USER"
else
  echo "L'utilisateur n'existe pas!"
fi```

## Exercice 5

```#!/bin/bash
read input
somme=1
for i in $(seq 1 $input);
do
  somme=$(( $i*$somme))
done

echo $somme```

## Exercice 6 :
```#!/bin/bash
random=$((1 + $RANDOM % 1000))
verif=true
while $verif; do
  read input
  
  if (( $input > $random )); then
    echo "Votre nombre est trop grand!"
  elif (( $input < $random )); then
    echo "Votre nombre est trop petit!"
  else
      verif=false
      echo "Bien joué vous avez trouvé le nombre!"
  fi
done```

## Exercice 7 :

```#!/bin/bash
declare -a arr=($1, $2, $3)
somme=0
for arr in ${arr[*]}
do  
  somme=$(( $i+$arr))
done

result=$((somme/3))
echo $result
echo ${arr[-1]}
echo ${arr[0]}```

```#!/bin/bash
declare -a arr=()
echo "Choisissez la quantité !"
read inputNb

for i in $(seq 1 $inputNb);
do
  read input
  arr+=($input)
done

somme=0
for arr in ${arr[*]}
do  
  somme=$(( $i+$arr))
done

result=$((somme/${#arr[@]}))
echo $result
echo ${arr[-1]}
echo ${arr[0]}```
