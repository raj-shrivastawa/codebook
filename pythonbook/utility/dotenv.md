# .env file support for Python
* `pip install python-dotenv` 

```python
# main.py
from dotenv import load_dotenv
import os

load_dotenv()
print(os.environ['myvar'])
```
By default it will look for .env file and if not there it will look for host level environment variable. For testing  

```bash
FROM python:3.11.9-alpine3.20
RUN pip install --upgrade pip && pip install python-dotenv
COPY main.py /home/project/app/main.py
WORKDIR /home/project/app/
USER 1000
ENTRYPOINT [ "python", "main.py" ]
```
* .env file
`myvar="1234567"`

```bash
docker build -t testenv .

docker run -ti --env myvar=1234 testenv /bin/sh
docker run -ti --env-file=.env testenv /bin/sh
```
