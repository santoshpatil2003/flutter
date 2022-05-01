# flutter (in this widgets are created)

import 'package:flutter/material.dart';



class Button extends StatefulWidget {
  const Button({required this.onPressed,required this.cat,required this.maxamount, Key? key}) : super(key: key);
  final GestureTapCallback onPressed;
  final String? cat;
  final String? maxamount;

  @override
  _ButtonState createState() => _ButtonState();
}

// List <Widget?> cat1 =  [a];

class _ButtonState extends State<Button> {

  // List <Widget?> cat1 =  [a];

  // void add(){
  //   cat1.add(b);
  //   setState(() {
  //   });
  // }

  @override
  Widget build(BuildContext context){
    // String? cat;
    // String? maxamount;

    return Padding(
      padding: const EdgeInsets.fromLTRB(20, 20, 20, 0),
      child: Container(
        height: 80,
        decoration: const BoxDecoration(
          color: Colors.white,
          boxShadow:[ BoxShadow(
            color: Colors.black45,
            spreadRadius: 2,
            blurRadius: 5,
          ),
          ],
          borderRadius: BorderRadius.all(Radius.circular(10)),
        ),
        child:Row(
          children: [
            Padding(
              padding: const EdgeInsets.fromLTRB(20, 0, 10, 0),
              child: Container(
                height: 60,
                width: 60,
                decoration: const BoxDecoration(
                  color: Colors.white,
                  boxShadow: [BoxShadow(
                    color: Colors.black45,
                    spreadRadius: 2,
                    blurRadius: 4,
                  ),],
                  borderRadius: BorderRadius.all(Radius.circular(50)),
                ),
              ),
            ),
             Padding(
              padding: const  EdgeInsets.fromLTRB(10, 0, 0, 0),
              child: Text(
                cat??="",
                style: const TextStyle(fontSize: 30.0),
              ),
            ),
              Padding(
              padding:  const EdgeInsets.fromLTRB(60, 5, 0, 0),
              child:  Text(
                maxamount??="",
                style: const TextStyle(fontSize: 30.0),
              ),
            ),
          ],
        ),
      ),
    );
  }
}

var a = Button(onPressed: (){},cat: cat,maxamount: maxamount,);
var b = Button(onPressed: (){},cat: cat,maxamount: maxamount,);

String? cat;
String? maxamount;


class Dict extends StatefulWidget {
  const Dict({Key? key}) : super(key: key);

  @override
  _DictState createState() => _DictState();
}

class _DictState extends State<Dict> {

  List<Widget?> cat1 = [];

  // padd() {
  //   return Future.delayed(const Duration(seconds: 5),add(),).then((value) => add());
  // }

  add() {
    return cat1.add(b);
  }

  // Future<void> add() async{
  //   return Future.delayed(const Duration(seconds: 2));
  //    // return cat1.add(b);
  // }

  popout(){
    Navigator.of(context).pop();
    setState(() {
    });
  }

  String? cat;
  String? maxamount;

  @override
  Widget build(BuildContext context) {

    return AlertDialog(
      title: const Text('Add new Category'),
      content: Column(
        mainAxisSize: MainAxisSize.min,
        crossAxisAlignment: CrossAxisAlignment.start,
        children:  <Widget> [
           TextField(
             onChanged: (text) {
               cat ??= text;
             },
            decoration: const InputDecoration(
                hintText: 'Name of Category'
            ),
          ),
           TextField(
             onChanged: (text) {
               maxamount ??= text;
             },
            decoration: const InputDecoration(
                hintText: 'Maximum Amount'
            ),
          ),
        ],
      ),
      actions: <Widget>[
        TextButton(
          onPressed: () {
            Navigator.of(context).pop();
          },
          child: const Text('Close'),
        ),
        TextButton(
          onPressed: () {
            popout().then((value) => add());
          },
          child: const Text('Submit'),
        ),
      ],
    );
  }
}


