# DAW_JoséMª
 Despliegue de aplicaciones Web

 # Actividad 0.5 - Práctica servidor web

En esta actividad, exploraremos el funcionamiento de un servidor web en Python utilizando la biblioteca `http.server`. A continuación, encontrarás enlaces a tres ejemplos de servidores web en Python que puedes ejecutar y experimentar:

## Ejemplo 1: Simple web server
- Documentación: [Simple web server (ejemplo 1)](https://docs.python.org/3/library/http.server.html)
- Ejecución: `python -m http.server 8000`


```python
import http.server as httpserver
import socketserver

def main(port=None):
	if port is None:
		port = 8000
	handler = httpserver.SimpleHTTPRequestHandler
	try:
		httpd = socketserver.TCPServer(("", port), handler)
		print("serving at port", port)
		httpd.serve_forever()
	except OSError:
		print("Given PORT:{} is unavailable.Try running with diffrent PORT Number!".format(port))

if __name__ == '__main__':
	main()```
