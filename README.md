# README

## Installation de Pandoc

Nous avons choisi d'utiliser Markdown , c'est pourquoi il est nécessaire d'utiliser l'outil **pandoc** (installer pandoc : <https://pandoc.org/installing.html>).

À cela il est aussi nécéssaire d'installer Latex pour pouvoir débloquer d'avantage de possibiliter de conversion (installer Latex : <https://doc.ubuntu-fr.org/latex#installation>).

## Conversions

Deux commandes préconfigurer sont mis à votre disposition pour passer de Markdown à un PDF ou un fichier HTML.

### Passage de .md à .html

Ainsi pour convertir notre fichier .md en fichier .html , il est nécessaire d'ouvrir un terminal , puis ensuite de ce possitionner dans le fichier Rapport_Technique. Une fois cela effectué , il ne reste plus qu'à effectuer la commande suivante :

```Bash
pandoc -d ./sources/Yaml/html.yml
```

Une fois cette commande effectuée , vous pourrez consulter le fichier Compte_Rendu.pdf se situant dans le dossier Rapport_Technique pour constater la conversion.

### Passage de .md à .pdf

Ainsi pour convertir notre fichier .md en fichier .pdf , il est nécessaire d'ouvrir un terminal , puis ensuite de ce possitionner dans le fichier Rapport_Technique. Une fois cela effectué , il ne reste plus qu'à effectuer la commande suivante :

```Bash
pandoc -d ./sources/Yaml/pdf.yml
```

Une fois cette commande effectuée , vous pourrez consulter le fichier Compte_Rendu.pdf se situant dans le dossier Rapport_Technique pour constater la conversion.
