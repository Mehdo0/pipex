# 🔧 Pipex

## 📘 Description

**Pipex** est un projet de l'école 42 qui consiste à reproduire en C le comportement des pipes (`|`) du shell Unix. Le programme prend en entrée un fichier, exécute une série de commandes en les chaînant via des pipes, et redirige la sortie vers un fichier de sortie.

## 🎯 Objectifs pédagogiques

- Comprendre et implémenter les redirections de fichiers (`<`, `>`, `<<`, `>>`).
- Manipuler les processus enfants avec `fork()`.
- Utiliser les pipes pour la communication inter-processus avec `pipe()`.
- Gérer les descripteurs de fichiers avec `dup2()`.
- Exécuter des commandes avec `execve()`.

## ⚙️ Compilation

Pour compiler le projet :

```bash
make
🚀 Utilisation
./pipex infile cmd1 cmd2 outfile
Ce qui équivaut à la commande shell suivante :

< infile cmd1 | cmd2 > outfile
Exemple
./pipex input.txt "grep a" "wc -l" output.txt
Cette commande lit input.txt, filtre les lignes contenant "a" avec grep, puis compte le nombre de lignes avec wc -l, et écrit le résultat dans output.txt.

🧪 Partie bonus
La partie bonus permet :

D'exécuter un nombre indéfini de commandes :

./pipex_bonus infile cmd1 cmd2 ... cmdn outfile
D'utiliser l'opérateur here_doc :

./pipex_bonus here_doc LIMITER cmd1 cmd2 outfile
Ce qui équivaut à :

cmd1 << LIMITER | cmd2 >> outfile
📁 Structure du projet
pipex/
├── src/            # Fichiers source
├── includes/       # Fichiers d'en-tête
├── Makefile        # Fichier de compilation
└── README.md       # Ce fichier

© 2025 – Projet Pipex – École 42