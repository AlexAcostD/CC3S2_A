prepare:
	python3 -m venv .venv
	. .venv/bin/activate 

run:
	PORT=8080 MESSAGE="Hola v1" RELEASE="v1" .venv/bin/python app.py

nginx:
	sudo cp nginx/miapp.conf /etc/nginx/sites-available/miapp
	sudo ln -sf /etc/nginx/sites-available/miapp /etc/nginx/sites-enabled/miapp
	sudo nginx -t
	# En WSL puede ser necesario usar service en vez de systemctl
	-sudo systemctl restart nginx || sudo service nginx restart

check-http:
	curl -s http://127.0.0.1:8080/

check-tls:
	curl -k https://miapp.local/

dns-demo:
	dig miapp.local
