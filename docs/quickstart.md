# Quick Start

This guide assumes you have a working understanding of Flask, and that you have already installed both Flask and Flask-RESTPlus. If not, then follow the steps in the Installation section.

## Initilization

As every other extension, you can initialize it with an application object:

    from flask import Flask
    from flask_restplus import Api

    app = Flask(__name__)
    api = Api(app)

or lazily with the factory pattern:

    from flask import Flask
    from flask_restplus import Api

    api = Api()

    app = Flask(__name__)
    api.init_app(app)

## A Minimal API

A minimal Flask-RESTPlus API looks like this:

    from flask import Flask
    from flask_restplus import Resource, Api

    app = Flask(__name__)
    api = Api(app)

    @api.route('/hello')
    class HelloWorld(Resource):
        def get(self):
            return {'hello': 'world'}

    if __name__ == '__main__':
        app.run(debug=True)

Save this as api.py and run it using your Python interpreter. Note that we’ve enabled Flask debugging mode to provide code reloading and better error messages.

    $ python api.py
    * Running on http://127.0.0.1:5000/
    * Restarting with reloader

`Warning:
 Debug mode should never be used in a production environment!`