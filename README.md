# vercel

## Congfiure djagno project

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
}```

- wsgi.py
```python
app = application
```

- settings.py
```python
ALLOWED_HOSTS = ['.vercel.app', '127.0.0.1']
```