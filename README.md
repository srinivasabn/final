11.
app.java
public int add(int a,int b)
return a+b;
main-build path-add lib-junit
src-apptest.java
app var=new app();
int a=4;
int b=var.add(2,2);
assertEquals(a,b);
run as junit

12.
mvn archetype:generate
write code
mvn package
mvn clean test
make changes and again mvn clean test

13.
mvn archetype:generate
code .
modify codes
open jenkins-freestyle
build-
cd C:\Users\Mohith\OneDrive\Desktop\raghuboss\sample
mvn test

14.
same steps as 12 till mvn package
in pom below build
<plugins>
      <plugin>
        <groupId>org.jacoco</groupId>
        <artifactId>jacoco-maven-plugin</artifactId>
        <version>0.8.11</version>
        <executions>
          <execution>
            <goals>
              <goal>prepare-agent</goal>
            </goals>
          </execution>
          <execution>
            <id>report</id>
            <phase>test</phase>
            <goals>
              <goal>report</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>
mvn clean test
goto target-site-index

15.
docker --version
docker ps
docker ps -a
docker images
docker run hello-world
docker pull nginx
docker run -d -p 8080:80 nginx
docker stop 'id'
docker rm 'id'

17.
docker run -d nginx
docker run -d -p 8088:80 nginx
docker volume create vol
docker run -it -v vol:/data ubuntu bash
cd /data
echo "hello world" > f1.txt
exit
docker run -it -v vol:/data ubuntu bash
cat /data/f1.txt
exit
docker run -d -p 8089:80 -v vol:/usr/share/nginx/html nginx
docker run -it -v vol:/data ubuntu bash
echo "<h1> good </h1>" > /data/index.html
exit


18.
two file app.py and Dockerfile
FROM python:3.9-slim

WORKDIR /app

COPY app.py .

CMD ["python", "app.py"]

docker build -t ram .
docker images
docker run ram
login dockerhub
docker tag ram mohithsk05/ram1:v1
docker push mohithsk05/ram1:v1



19
docker build -t java-app .
docker run -d -t java-app

16
app.py,Dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY app.py .
EXPOSE 5020
CMD ["python", "app.py"] 

app.py
from http.server import SimpleHTTPRequestHandler, HTTPServer
PORT = 5020
class MyHandler(SimpleHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header("Content-type", "text/html")
        self.end_headers()
        self.wfile.write(b"<h1>Hello from Docker Python Container</h1>")

server = HTTPServer(("0.0.0.0", PORT), MyHandler)
print(f"Server running on port {PORT}...")
server.serve_forever()

docker build -f Dockerfile -t my-first-app .
docker run -p 5020:5020 my-first-app

20
https://github.com/SarveshG2005/exp20.git
docker background,git codes
pipeline project
script from scm
none-git
paste url,credentials
save,build
console op-local host - web page
