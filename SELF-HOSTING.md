# Self Hosting

1. To host this yourself, download all of the code files. This guide requires Python and a little knowledge of computers.
2. Open `main.py` and change the `adminkey`. This is the password you will use to add or remove quotes from your API.
3. Open the folder containing the files in a terminal and run these commands:
4. `python -m venv .venv`
5. `source .venv/bin/activate`. On Windows, use `.venv\Scripts\activate` instead.
6. `pip install fastapi uvicorn`
7. `uvicorn main:app --host 0.0.0.0 --port 8000`
8. Your API is now running on port `8000`.
9. There are four commands you can use with your API:
10. `example.com/get`
11. `example.com/list`
12. `example.com/add/"quote here"/adminkey`
13. `example.com/remove/"quote index number here from /list"/adminkey`
14. Replace `example.com` with your domain or IP address. You can search online for how to set up a domain or find your IP address. Also replace `adminkey` with the `adminkey` you set in `main.py`.
15. When adding a quote, replace every space with `%20`. For example, `Hello world` becomes `Hello%20world`.
16. Adding and removing quotes use POST requests. In a terminal, use `curl -X POST` followed by the URL.
17. For example, to add a quote: `curl -X POST "example.com/add/Hello%20world/adminkey"`
18. To remove a quote, first use `/list` to find its index number, then run: `curl -X POST "example.com/remove/3/adminkey"`
19. Keep your `adminkey` private. Anyone who has it can add or remove quotes from your API.
20. If you want to receive updates from the original repository, use Git instead of simply downloading the files. Clone the repository with `git clone`, and later use `git pull` inside the repository folder to get the latest updates.
21. To clone the repository, run `git clone <repository-url>` and replace `<repository-url>` with the URL of the repository.
22. After cloning, open the new repository folder in your terminal and follow the setup steps above.
