### Page de connnexion


```js
connect(serial_number, password)

	user = get_user_from_database(serial_number)


	else if user.password==password:
		ifuser.first_connection == True
			post("set_password.html")
		else
			post("Homepage.html")
	else
		erreur: mauvais mot de passe
```

```js
forgotten_password()
	post("page_demande_matricule.html")

```

### Page de récupération de mot de passe
```js
send_serial_for_password_reset(serial_number)

	if serial_number in database
		code_in_ram =create_code()
		send_email(get_user().email, code)
		post("verification code.html")

	else
		return erreur: pas de serial number dans la database
```

### Page de saisie de code de vérification
```js
send_verification_code(code)

	if code == code_in_ram
		post("set_password.html")
	else
		return erreur
```
### page de modification de mot de passe

```js
modify_password(password1, password2)
	if password1 != password2
		return erreur: pas egaux

	if check_pass_validity(password1) == False:
		return erreur: pas conforme

	user = getUser()
	user.password = hash(password1)
	setuser(user)

```