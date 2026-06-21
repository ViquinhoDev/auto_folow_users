# **auto_follow_users**

<img width="1920" height="1080" alt="Captura de tela 2026-06-21 161701" src="https://github.com/user-attachments/assets/677248ce-031b-4de7-9a36-cab75b5a18ce" />

**Description**

Auto Follow Users is a Python automation script that helps you quickly follow multiple GitHub users. The script requests your GitHub credentials and the number of users you want to follow, then automatically searches for random users and follows them.

**Features**

- Automated GitHub user discovery and following
- Secure credential authentication using GitHub tokens
- Random user selection from GitHub's database
- Color-coded terminal output for better visibility
- Error handling and rate limit management
- Simple and intuitive command-line interface

**Requirements**

- Python 3.6 or higher
- GitHub account and personal access token
- Required libraries: `requests`, `colorama`

**Installation**

1. Clone the repository:
```bash
git clone https://github.com/ViquinhoDev/auto_follow_users.git
cd auto_follow_users
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install requests colorama
```

3. Generate a GitHub Personal Access Token:
   - Go to GitHub Settings → Developer settings → Personal access tokens
   - Click "Generate new token"
   - Grant the `user:follow` scope
   - Copy your token (you'll need it when running the script)

**Usage**

Run the script:
```bash
python main.py
```

Follow the prompts:
1. Enter your GitHub username
2. Enter your GitHub personal access token
3. Specify the number of users you want to follow

The script will then automatically search for and follow the specified number of random GitHub users.

**Example**

```
Please log in with your GitHub credentials.
GitHub Username: ViquinhoDev
GitHub Token: ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
Welcome, ViquinhoDev! Authentication successful.
How many people would you like to follow: 50
Searching 50 random users...
Followed: user1
Followed: user2
...
```

**How It Works**

- **Authentication**: Validates your GitHub credentials using the API
- **User Fetching**: Retrieves random users from GitHub's public user list
- **Following**: Automatically follows selected users using the GitHub API
- **Rate Limiting**: Implements delays to avoid hitting GitHub's rate limits

**Configuration**

You can modify the behavior in `main.py`:

- **Delay between requests**: Adjust `time.sleep(1)` to change rate limiting
- **Users per page**: Modify `per_page=100` in the API request
- **Randomization**: Users are randomly selected from the fetched list

**Requirements.txt**

```
requests==2.31.0
colorama==0.4.6
```

**Important Notes**

⚠️ **Disclaimer**: This tool should be used responsibly and in accordance with GitHub's Terms of Service. Excessive automated following may result in rate limiting or account restrictions.

- GitHub has rate limits for API requests
- Use reasonable numbers for following users
- Respect GitHub's community guidelines

**Error Handling**

- **Authentication failed**: Check your username and token
- **Rate limit exceeded**: Wait a few minutes before trying again
- **Invalid input**: Ensure you enter a positive number

**Troubleshooting**

| Error | Solution |
|-------|----------|
| "Invalid Token" | Regenerate your GitHub token and ensure it has user:follow scope |
| "Unexpected EOF while parsing" | Ensure your Python version is 3.6 or higher |
| "Connection timeout" | Check your internet connection and try again |
| "Rate limit" | Wait before running the script again |

**Security Notes**

- Never share your GitHub token
- Don't hardcode credentials in the script
- Use environment variables or `.env` files for storing tokens in production
- Tokens should have minimal required scopes

**Contributing**

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

**License**

This project is licensed under the MIT License - see the LICENSE file for details.

**Disclaimer**

This tool is provided for educational purposes. Users are responsible for their own actions and must comply with GitHub's Terms of Service and all applicable laws and regulations. Misuse of this tool may result in account restrictions or bans.

---

**Quick tip**: Save your script requirements to a file by running:
```bash
pip freeze > requirements.txt
```
