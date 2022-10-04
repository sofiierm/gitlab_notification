# gitlab_notification
The service for notifications about gitlab events.

1. Clone a repository
2. Create a webhook in the gitlab repository where the notifications will come from  (https://gitlab.com/{project_path}/-/hooks Settings -> Webhooks)
- URL - http://ip:port/callback/
- disabled SSL verification
- only supported triggers: Push Events, Issue Events, Note Events
3. In the file notifications-bot/gitlab_bot/app/tg_sender.py change chat_dict
- key - Gitlab Project ID, found in every repository on the main page, the project that will be notified
- value - telegram chat id (you can get it for example here https://t.me/RawDataBot) chat, which will receive notifications
4. In the file notifications-bot/gitlab_bot/app/tg_sender.py change the TOKEN of the bot, you can get it from https://t.me/BotFather 
5. From the directory notifications-bot/ start Docker:
- docker-compose build
- docker-compose up
