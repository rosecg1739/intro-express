# intro-express


const express = require('express');

const app = express();

app.get('/', function(req, res) {
    res.send('<h1>Hello World!</h1>');
});



app.listen(3000, function() {
    console.log('listening on port 3000');
});


const home = require('./routes/home');
const { path } = require('express/lib/application');
app.use('/', home);

app.get('/', function(req, res) {
    res.send('<h1>home page</h1>');
});

app.set('view engine', 'ejs');

app.set('views', path.join(__dirname, 'views'));

const express = ('express');
const path = require('path');


// data/todo-db.js

const students = [
    {student: 'homework', done: true},
    {student: 'Learn Express', done: false},
    {student: 'Billyy   ', done: false}
  ];

  module.exports = {
    getAll: function() {
      return students;
    }
  };

  const path = require('path');

// require the To Do "database"
const students = require('./data/students-db');

app.get('/students', function(req, res) {
    res.render('students/index', {
      students: studentsDb.getAll()
    });
  });

  app.get('/', function(req, res) {
    res.redirect('/home');
  }); 

  

