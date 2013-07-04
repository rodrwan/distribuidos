import json
from bottle import route, run, request, abort, response

users = {
    '0': {
        'first_name': 'nombre0',
        'last_name': 'apellido0'
    },
    '1':{
        'first_name':'nombre1',
        'last_name':'apellido1'
    }
} 
@route('/users', method='GET')
def getUsers():
    try:
        response.content_type = 'text/json; charset=utf-8'
        return json.dumps({ 'data' : users }, indent=4, separators=(',', ': '))
    except:
        abort(404, 'Error algo salio mal.')

@route('/users/:id', method='GET')
def getUser(id):
    try:
        entity = id.split(".")
        if entity[1] == "json":
                response.content_type = 'text/json; charset=utf-8'
                return json.dumps({'data' : users[entity[0]]}, indent=4, separators=(',', ': '))
        if entity[1] == "":
                abort(404, 'No username with id %s' % id)
        return entity
    except:
        abort(404, 'Error en parametros, falto .json')

@route('/users/new', method='POST')
def setUser():
        first_name = request.forms.get('first_name')
        last_name  = request.forms.get('last_name')
	users[str(len(users))] = {
		'first_name': first_name,
		'last_name' : last_name
	}
        return json.dumps({'data':'usuario ingresado\n'}, indent=4, separators=(',', ': '))

 
run(host='localhost', port=8080, debug=True)

