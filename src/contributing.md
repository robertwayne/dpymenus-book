# Contributing

I am open to all contributions, so long as it fits within the scope of the library. Large or breaking changes should be
discussed via issue before submitting a PR, but smaller changes can be submitted directly for review.

## Scope

The overall scope for the project is as follows:

- Implement a simple-to-use API for creating menus with discord.py
- Support various styles of commonly-used menus out of the box
- Supply easy-to-override abstractions and settings across menus
- Supply generally useful default settings & constants
- Offer full documentation on all features via the book, examples, and docstrings.

## Building

This library is built against a minimum version of Python 3.8.

`dpymenus` uses the **[Poetry](https://python-poetry.org/)** package manager to manage dependencies and builds. Make sure
you have Poetry installed via the **[official installation instructions](https://python-poetry.org/docs/#installation)**.

1. Clone the repository and checkout the `next` branch:

   ```shell
   git clone https://github.com/robertwayne/dpymenus
   ```

   ```shell
   cd dpymenus
   ```

   ```shell
   git checkout next
   ```

2. (Optional) Set up the example runner, so you can test your changes live. Create a `.env` file:

    ```shell
    echo "BOT_TOKEN=your_private_token_here" > .env
    ```

   > **Windows Users**
   >
   > Due to the way Windows creates new files, the simplest solution is to just
   > create a .env in VSCode or your IDE of choice. Using the above will cause you
   > to receive an encoding error, as the file will not be in UTF-8.

   *Note: Replace the `your_private_token_here` text with the token from your
   **[Discord Developers](https://discord.com/developers/applications)**
   bot page. If you are unsure what to use, please see the
   **[discord.py guide](https://discordpy.readthedocs.io/en/stable/discord.html)**.*

3. Install the dependencies:

    ```shell
    poetry install
    ```

4. (Optional) Test that the runner is working with:

    ```shell
    poetry run examples
    ```

   If the bot starts, and you can run commands in whatever server you have added the bot to, you are ready to go!

## Pull Requests

1. Fork the repository and create your branch from `next`.
2. Ensure any public API changes are reflected in the book, the relevant example, and docstrings.
3. Ensure you have tested your changes, and added any tests for functions which are not directly using `discord.py`.
4. Submit the PR! ✨

## Coding Style

`dpymenus` uses a built-in **[black](https://github.com/psf/black)** configuration to handle formatting. Your code will
automatically be formatted on submission via GitHub actions, but you can run `poetry run fmt` to manually format it.

- Follow PEP8 naming conventions.
- Break up dense chunks of code where it makes sense (if/else try/catch, returns).
- Ensure docstrings follow existing docstring structure.
- All library code should be type annotated. Examples should not.
  - See the `dpymenus/types/__init__.py` file for existing built-in library types.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
