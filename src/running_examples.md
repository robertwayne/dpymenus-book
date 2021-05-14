# Running Examples

`dpymenus` contains a working example for almost every feature most developers will be using. All the examples run as separate cogs on a bot that you can load up yourself.

All of these instructions should work on Linux (Ubuntu-flavors) & Windows 10.

> **Windows Users**
>
> Windows can be pretty finicky with PATH and Python installations sometimes.
> If you are having issues installing Poetry, ensure that your PATH contains a
> `%USERPROFILE%\.poetry\bin\` string.
>
> In addition, you probably want to go into App Execution Aliases and turn off any
> options relating to Python and install Python from [python.org](https://python.org).

In your command line *(PowerShell if you are on Windows)*:

1. Clone the repository.

    ```shell
    git clone https://github.com/robertwayne/dpymenus
    ```

2. Move into the directory you just cloned.

    ```shell
    cd dpymenus
    ```

3. We need to create a `.env` file and add a token to it.

    ```shell
    echo "DPYMENUS_BOT_TOKEN=your_private_token_here" > .env
    ```

   > **Windows Users**
   >
   > Due to the way Windows creates new files, the simplest solution is to just
   > create a .env in VSCode or your IDE of choice. Using the above will cause you
   > to receive an encoding error, as the file will not be in UTF-8.

   Replace the `your_private_token_here` text with the token from your
   **[Discord Developers](https://discord.com/developers/applications)**
   bot page. If you are unsure what to use, please see the
   **[discord.py guide](https://discordpy.readthedocs.io/en/stable/discord.html)**.

4. Install Poetry and the project dependencies.

    ```shell
    pip -m install poetry && poetry install
    ```

   > Please note that this is not the preferred way to install Poetry. Instead,
   > you should follow the **[guide](https://python-poetry.org/docs/#installation)** on their site.
   > I highly recommend Poetry as a package manager for Python, so it is not wasted
   > effort to download and learn properly.

5. Run the bot!

    ```shell
    poetry run examples
    ```

At this point, the bot should be up and running. All the cogs are loaded automatically thanks to **[cogwatch]('https://github.com/robertwayne/cogwatch)**, so you can add the bot to your server and start using commands.
