# Bitcoin TXID Checker
### Bitcoin transaction ID confirmation checker using Discord Webhook. 

Quite self-explanatory, fill in some essential information, run the script then input a couple values and it will notify you in the Discord server channel that you chose using webhook when your BTC TXID is confirmed in the blockchain.

## Requirements:
1. python3
2. dhooks
3. Your own Discord Webhook URL

## Instructions for absolute beginners:
1. Install Python from [python.org](https://www.python.org/).
2. Go to [releases](https://github.com/opp/Bitcoin-TXID-Checker/releases/latest) to download & extract the `Source code.zip` file. Make sure all the files are inside the same folder. 
3. Install `requirements.txt` using Pip.
	> Navigate into the folder using `cd` in your CMD (Windows) or terminal (Unix). Look it up if you're unsure how to do that. Once inside the folder do `pip install -r requirements.txt` for Windows. For Linux/Mac do `pip3 install -r requirements.txt`. If you encounter an error here then you did something wrong while installing Python.
4. In Discord, go to `User Settings` -> `Appearance` -> scroll until you find `Advanced` category -> enable `Developer Mode`. ([Picture example.](https://i.imgur.com/HHaqOXy.png))
5. In Discord, create a new server. Create a channel where you want to display the message when your TXID confirms (must be a text channel). Go to that channel's settings -> `Integrations` -> in Webhooks category click `Create Webhook`. Change name & avatar if you want to. ([Picture example.](https://i.imgur.com/6TsJWSP.png))
    > Do not share the webhook URL with anybody.
6. Open `settings.json` from the folder you downloaded and extracted.
7. Go to the webhooks settings in Discord just like before and copy the webhook URL, ([picture example](https://i.imgur.com/S4NoLKN.png)), then replace the text inside the quotations after `"webhook":` in `settings.json` file with the webhook URL you just copied. **KEEP** the quotations around the URL.
    > Your `settings.json` file should look something like this now.
    ```json
    {
        "webhook": "https://discord.com/api/webhooks/.../...",
        "userID": REPLACE_THIS_TEXT_WITH_YOUR_DISCORD_ID___DO_NOT_PUT_ANY_QUOTATIONS_HERE
    }
    ```
    > The '...' portion is different for each webhook URL.
8. Go back to the server you created and right click your profile from the member list. Click on `Copy ID` ([picture example](https://i.imgur.com/b09zLmz.png)) and paste that after `"userID":` in `settings.json`. **DO NOT** put quotations around this.
    > Your `settings.json` file should look something like this now.
    ```json
    {
        "webhook": "https://discord.com/api/webhooks/.../...",
        "userID": 362181701373263875
    }
    ```
    > Each user has an unique userID; yours should be different from the example above.
9. Save the `settings.json` file and close it. In most cases you'll never need to touch it ever again. After you're done tweaking the `settings.json` once again make sure that all files are inside the same folder.
10. Open your terminal, or command prompt for Windows (no need to open as admin), and navigate inside the folder just like in step 3.
11. Once inside the folder, type `python main.py` for Windows or `python3 main.py` if you're on Linux or Mac to run the script. Follow what the script prompts from then on.

## Some things to note:
1. If you ever delete the server, channel, or start using new Discord account you'll have to update settings.json accordingly.
2. While inputting TXID, only input the TXID/hash not a URL. For example, do not put in `https://www.blockchain.com/btc/tx/5d9ef693d41cb3bb4c6d98e70ea8b2cc91be29a804245a06ec8761d9cddc103c`, instead just input `5d9ef693d41cb3bb4c6d98e70ea8b2cc91be29a804245a06ec8761d9cddc103c`.
4. If you don't say how frequently you want to check the blockchain, a 'default' interval will be set which is set to check every 60 seconds. Quickest you can check is 30 seconds but since this is open source you can obviously edit that value yourself. I wouldn't recommened going lower as you might get your IP banned from the API but do as you wish not my problem.
