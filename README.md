# Vercel

## Configuration

#### deployment on vercel
- vercel.json
```json
{
    "builds":[{
        "src": "project/wsgi.py",
        "use": "@vercel/python",
        "config": { "maxLambdaSize": "15mb"}
    }],
    "routes": [{
        "src": "/(.*)",
        "dest": "project/wsgi.py"
    }]
}
```

- wsgi.py
```python
application = get_wsgi_application()
app = application
```

- settings.py
```python
ALLOWED_HOSTS = ['.vercel.app']
```
#### securly save secret data
python-decouple to store secret data | create .env file
```python
from decouple import config

```