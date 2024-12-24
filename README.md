- 👋 Hi, I’m @Gamingbeast482
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
- 😁 i'm mobile user ...
<!---
Gamingbeast482/Gamingbeast482 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import requests

# Replace with your GitHub username and personal access token
GITHUB_USERNAME = "your_username"
GITHUB_TOKEN = "your_personal_access_token"

def fetch_user_repositories(username):
    url = f"https://api.github.com/users/{username}/repos"
    headers = {
        "Authorization": f"token {GITHUB_TOKEN}",
    }
    response = requests.get(url, headers=headers)

    if response.status_code == 200:
        repos = response.json()
        for repo in repos:
            print(f"Repository: {repo['name']}")
            print(f"Description: {repo['description']}")
            print(f"URL: {repo['html_url']}")
            print("-" * 40)
    else:
        print(f"Failed to fetch repositories. Status code: {response.status_code}")
        print(response.json())

if __name__ == "__main__":
    username = input("Enter the GitHub username: ")
    fetch_user_repositories(username)
