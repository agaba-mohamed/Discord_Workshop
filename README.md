# Guide de création d'un bot Discord avec discord.js

## Introduction

discord.js est une bibliothèque JavaScript permettant de créer des bots pour la plateforme Discord. Ce workshop vous aidera à créer votre premier bot Discord étape par étape.

## Prérequis

- Node.js installé sur votre machine
- Accès à Discord Developer Portal pour créer une application et obtenir un token de bot

## Étape 1 : Configuration initiale

1. Créez un nouveau répertoire pour votre projet et ouvrez-le dans votre éditeur de texte.
2. Dans le terminal, initialisez un nouveau projet Node.js en exécutant la commande suivante :
   ```bash
   npm init -y
   ```

## Étape 2 : Installation des dépendances

Installez la bibliothèque discord.js en exécutant la commande suivante :

```bash
npm install discord.js
```


## Étape 3 : Configuration sur Discord Developer Portal

1. Rendez-vous sur [Discord Developer Portal](https://discord.com/developers/applications) et connectez-vous à votre compte Discord.
2. Cliquez sur le bouton "New Application" pour créer une nouvelle application.
3. Donnez un nom à votre application, puis naviguez vers l'onglet "Bot" dans le menu latéral.
4. Sous la section "TOKEN", cliquez sur "Copy" pour copier le token de votre bot. Vous en aurez besoin pour la configuration dans votre code.

## Étape 4 : Création du bot

1. Créez un fichier nommé `bot.js` dans votre répertoire.
2. Ouvrez `bot.js` et ajoutez le code suivant pour importer la bibliothèque et créer un nouveau client :

```javascript
const Discord = require('discord.js');
const client = new Discord.Client({ intents: [
    Discord.GatewayIntentBits.Guilds,
    Discord.GatewayIntentBits.GuildMessages,
    Discord.GatewayIntentBits.MessageContent
]})
```

## Étape 5 : Événements du bot

Ajoutez des événements pour gérer la connexion et les messages :

```javascript
client.once('ready', () => {
    console.log('Bot is online!');
});

client.on('messageCreate', (message) => {
    if (message.content === 'ping'){
        message.reply('Pong!')
    }
});

client.login('VOTRE_TOKEN');
```

Remplacez `VOTRE_TOKEN` par le token de votre bot obtenu depuis Discord Developer Portal.

## Étape 6 : Lancement du bot

Dans votre terminal, exécutez la commande suivante pour démarrer votre bot :

```bash
node bot.js
```

Votre bot devrait maintenant être en ligne et répondre au message `!ping`.

## Conclusion

Félicitations ! Vous avez créé votre premier bot Discord avec discord.js. Vous pouvez maintenant continuer à ajouter des fonctionnalités supplémentaires à votre bot selon vos besoins.
