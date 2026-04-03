
    def worker():
        global naif
        while True:
            try:

                rnd = str(random.randint(150, 999))
                user_agent_str = (
                    "Instagram 311.0.0.32.118 Android ("
                    + random.choice(["23/6.0", "24/7.0", "25/7.1.1", "26/8.0", "27/8.1", "28/9.0"])
                    + "; "
                    + str(random.randint(100, 1300))
                    + "dpi; "
                    + str(random.randint(200, 2000))
                    + "x"
                    + str(random.randint(200, 2000))
                    + "; "
                    + random.choice(["SAMSUNG", "HUAWEI", "LGE/lge", "HTC", "ASUS", "ZTE", "ONEPLUS", "XIAOMI", "OPPO", "VIVO", "SONY", "REALME", "INFINIX"])
                    + "; SM-T"
                    + rnd
                    + "; SM-T"
                    + rnd
                    + "; qcom; en_US; 545986"
                    + str(random.randint(111, 999))
                    + ")"
                )

                Id = rand_ids(ids_1)
                lsd = ''.join(random.choices('abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789', k=32))

                headers = {
                    'accept': '*/*',
                    'accept-language': 'en,en-US;q=0.9',
                    'content-type': 'application/x-www-form-urlencoded',
                    'dnt': '1',
                    'origin': 'https://www.instagram.com',
                    'priority': 'u=1, i',
                    'referer': 'https://www.instagram.com/cristiano/following/',
                    'user-agent': user_agent_str,
                    'x-fb-friendly-name': 'PolarisUserHoverCardContentV2Query',
                    'x-fb-lsd': lsd,
                }

                data = {
                    'lsd': lsd,
                    'fb_api_caller_class': 'RelayModern',
                    'fb_api_req_friendly_name': 'PolarisUserHoverCardContentV2Query',
                    'variables': '{"userID":"' + str(Id) + '","username":"cristiano"}',
                    'server_timestamps': 'true',
                    'doc_id': '7717269488336001',
                }

                response = requests.post('https://www.instagram.com/api/graphql', headers=headers, data=data)



                try:
                    resp_json = response.json()
                except Exception:
                    resp_json = {}

                user_data = resp_json.get('data', {}).get('user', {})
                if not user_data:
                    continue

                username = user_data.get('username', '')
                follower_count = user_data.get('follower_count', 0)
                is_private = user_data.get('is_private', True)
                id_user = user_data.get('pk')

                if not username or username in found_usernames_1:
                    continue



                if any(x in username for x in ["_"]) or len(username)<8:
                    continue




                if is_private or follower_count>60:
                    continue


                found_usernames_1.add(username)
                email=username+'@gmail.com'
                check(email)








            except Exception as e:

                continue


    for _ in range(60):
        Thread(target=worker).start()

if ch == "1":
        uid1= 210468786
        uid2 = 269736186
        collect_users_1()
elif ch == "2":
        uid1= 310438486
        uid2 = 495999999
        collect_users_1()
elif ch == "3":
        uid1= 1219010000
        uid2 = 1429010000
        collect_users_1()
elif ch == "4":
        uid1= 1700000000
        uid2 = 2400000000
        collect_users_1()
elif ch == "5":
        uid1= 3313668786
        uid2 = 3713668786
        collect_users_1()
elif ch == "6":
        uid1= 5398785217
        uid2 = 5999785217
        collect_users_1()

elif ch == "7":
        uid1= 7497939245
        uid2 = 8597939245
        collect_users_1()
elif ch == "8":
        uid1= 11254029834
        uid2 = 21254029834
        collect_users_1()
elif ch == "9":
        uid1= 40064475395
        uid2 = 43464475395
        collect_users_1()
else:
        pass
