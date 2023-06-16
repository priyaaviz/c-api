# CODE
# GET


``` py
@app.route('/gad', methods=['GET','POST'])
def gad():
    if request.method=='GET':
        if len(gadgets)>0:
            return jsonify(gadgets)
        else:
            "nothing"
```
# POST
``` py
    if request.method=='POST':
        new_name=request.form['name']
        new_class=request.form['class']
        iD=gadgets[-1]['id']+1

        new_gad={
            'id':iD,
            'name':new_name,
            'class':new_class
        }
        gadgets.append(new_gad)
        return jsonify(new_gad)
```

#  GET 
* GET- To retrieve the specific data by providing `id`.
``` py
app.route('/gad/<int:id>', methods=['GET','PUT', 'DELETE'])
def get_gad(id):
    if request.method=='GET':
        for gad in gadgets:
            if gad['id']== id:
                return jsonify(gad)
            else:
               pass
```
# PUT
``` py
 if request.method=='PUT':
        for gad in gadgets:
            if gad['id']== id:
                gad['name']=request.form['name']
                gad['class']=request.form['class']
                update_book={
                    'name':gad['name'],
                    'class':gad['class']

                }
                return jsonify(update_book)
```
# DELETE
``` py
 if request.method=='DELETE':
        for index, gad in enumerate(gadgets):
            if gad['id']==id:
                gadgets.pop(index)
                return jsonify(gadgets)
```


