# djangostripe 

## Video Demonstration

Link: https://youtu.be/7om_bC6I7zY

## Necessary Modifications

1. Add your Stripe secret and publishable keys to the *settings.py* file:

    ```python
    STRIPE_PUBLISHABLE_KEY = '<your test publishable key here>'
    STRIPE_SECRET_KEY = '<your test secret key here>'
    ```

1. Add the webhook endpoint secret from Stripe to the *settings.py* file:

    ```python
    STRIPE_ENDPOINT_SECRET = '<your endpoint secret here>'
    ```

1. Change "DEBUG" to False and add the production site to "ALLOWED_HOSTS" in the *settings.py* file:

    ```python
    DEBUG = True

    ALLOWED_HOSTS = []
    ```

1. Edit product information in the *views.py* file:

    ```python
    line_items=[{
                    
        'price_data': {
            'currency': 'usd',
            'unit_amount': '3000',
            'product_data': {
                'name': 'Sneakers',
            }
        },

        'quantity': 1,

    }],
    ```


## Run the Solution Locally


1. Install the requirements:

    ```sh
    (venv)$ pip install -r requirements.txt
    ```

1. Apply the migrations:

    ```sh
    (venv)$ python manage.py migrate
    ```

1. Run the server:

    ```sh
    (venv)$ python manage.py runserver
    ```
