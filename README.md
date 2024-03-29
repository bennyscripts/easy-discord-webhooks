# easy-discord-webhooks
An easy and simplistic way to execute and modify a Discord webhook all from Python.  

### Install
```
pip install easy-discord-webhooks
```

### Examples
  
Sending `hello world` to a webhook.
```python
import easy_discord_webhooks as DiscordWebhooks # Import easy-discord-webhooks as something easy to refer back to.

webhookUrl = "WEBHOOK_URL_HERE"
webhook = DiscordWebhooks.Webhook(webhookUrl) # Create a new webhook object with your webhook URL.

webhook.send("Hello World") # Send a hello world to the webhook using the objects send function.
```
  
<br />
  
Sending a basic embed to a webhook.
```python
import easy_discord_webhooks as DiscordWebhooks # Import easy-discord-webhooks as something easy to refer back to.

webhookUrl = "WEBHOOK_URL_HERE"
webhook = DiscordWebhooks.Webhook(webhookUrl) # Create a new webhook object with your webhook URL.

embed = DiscordWebhooks.Embed( # Create an embed object.
  title="Embed Title", # Set the title
  description="Embed description...", # Set the description
  color="#ff0000" # Set the color (must be a hex value)
)

webhook.send("Hello World", embed=embed) # Send a hello world + the embed to the webhook using the objects send function.
```
  
<br />
  
Sending an advanced embed with fields and images to a webhook.
```python
import easy_discord_webhooks as DiscordWebhooks # Import easy-discord-webhooks as something easy to refer back to.

webhookUrl = "WEBHOOK_URL_HERE"
webhook = DiscordWebhooks.Webhook(webhookUrl) # Create a new webhook object with your webhook URL.

embed = DiscordWebhooks.Embed( # Create an embed object.
  title="Embed Title", # Set the title
  description="Embed description...", # Set the description
  color="#ff0000" # Set the color (must be a hex value)
)

# Add fields using add_field function
embed.add_field(name="Field 1", value="Field 1 value.") 
embed.add_field(name="Field 2", value="Field 2 value.")
embed.add_field(name="Field 3", value="Field 3 value.")

# Set an image with set_image
embed.set_image(url="https://discord.com/assets/ff41b628a47ef3141164bfedb04fb220.png")

# Set a thumbnail image with set_thumbnail
embed.set_thumbnail(url="https://discord.com/assets/f9bb9c4af2b9c32a2c5ee0014661546d.png")

webhook.send("Hello World", embed=embed) # Send a hello world + the embed to the webhook using the objects send function.
```
  
<br />
  
Gather info about a webhook.
```python
import easy_discord_webhooks as DiscordWebhooks # Import easy-discord-webhooks as something easy to refer back to.

webhookUrl = "WEBHOOK_URL_HERE"
webhook = DiscordWebhooks.Webhook(webhookUrl) # Create a new webhook object with your webhook URL.

# get some information from the webhook
username = webhook.name
id = webhook.id
avatar = webhook.avatar
token = webhook.token

# other variables that could come in handy
guildId = webhook.guildId
channelId = webhook.channelId
applicationId = webhook.applicationId
type = webhook.type

# print the information we got from the webhook
print("Webhook name:", username)
print("Webhook id:", id)
print("Webhook token:", token)
print("Webhook avatar:", avatar)
```
