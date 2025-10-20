
```js
// reception requete connection classique avec login + password /login

user = get_user_from_database(login)

if user.first_connection == True
	post("set_password.html")

else if user.password==hash(password):
	post("Homepage.html")

else
	post("Connection_Failed.html")
```

```js
// reception requete changement password ave   /forgotten_password
	post("page_demande_matricule.html")

```
```js
// reception requete reinitialisation mdp avec matricule /send_tresor

	if matricule in database
		code_in_ram =create_code()
		send_email(get_user().email, code)
		post("verification code.html")

	else
		return erreur
```
```js
// reception requete code verification /send_verif

	if code == code_in_ram
		post("set_password.html")
	else
		return erreur
```
```js
// reception set password /change_pass
	if pass1 != pass2
		return erreur pas egaux

	if check_pass_validity(pass1) == False:
		return erreur pas conforme

	user = getUser()
	user.password = hash(pass1)
	setuser(user)

```