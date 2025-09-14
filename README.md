# Instagram Automation with Selenium and Python

## Overview
This project automates various Instagram activities using Selenium and Python, including login, searching profiles, following/unfollowing users, liking/unliking posts, extracting followers, and viewing stories.

---

## 📚 Libraries Used
```python
import selenium
from selenium import webdriver
from selenium.common.exceptions import NoSuchElementException
from selenium.webdriver.common.keys import Keys 
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.by import By
from bs4 import BeautifulSoup as bsp
import bs4
import time
import pandas as pd
```


⚙️ Setup

Setup username and password variables.

Setup Chromedriver path.

Initialize WebDriver and open Instagram site.

✅ Features Implemented
1️⃣ Login to Instagram

Function log_in_to_account(driver, username, password) logs into an Instagram account.

2️⃣ Search for Handles

Function Search_Handle(driver, string) searches and returns a list of handles based on the input string.

3️⃣ Open Profile

Function search_open(driver, profile) searches and opens the specified profile.

4️⃣ Follow / Unfollow

Functions:

follow(driver, profile)

unfollow(driver, profile)

Follow or unfollow a specified profile.

5️⃣ Like / Unlike Posts

Functions:

like(driver, profile, no_of_post)

unlike(driver, profile, no_of_post)

Like or unlike a specified number of posts from a given profile.

6️⃣ Extract Followers

Functions:

extracting_followers(driver, profile, no_of_followers)

extract_followers_of_profiles(driver, names, no_of_followers)

extracting_all_followers(driver, profile, username, no_of_followers)

extracting_all_following(driver, profile, username)

followers_follow_profile_not_mine(driver, profiles)

Extract followers and followings from a profile, and filter followers who follow a profile but do not follow back the user.

7️⃣ View Stories

Function story(driver, profile) checks and views stories from a given profile.

🚀 Example Usage
```Python
profile = "So Delhi"
login = log_in_to_account(driver, username, password)

if login:
    handle_list = Search_Handle(driver, "food")
    open_ = search_open(driver, profile)
    follow_status = follow(driver, profile)
    unlike_status = unlike(driver, profile, 30)
    followers = extracting_all_followers(driver, profile, username)
    story(driver, profile)
```

⚠️ Closing Driver

At the end of the process:
```Python
driver.close()
```

⚡ Note

Fill in your Instagram credentials and update Chromedriver path accordingly.

Customize the parameters such as profile, no_of_post, and no_of_followers as needed.

This automation is for educational purposes. Please adhere to Instagram's policies.
