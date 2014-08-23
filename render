#!/usr/bin/env node

var fs = require('fs');

if (!fs.existsSync(process.argv[2]) || !fs.existsSync(process.argv[3])) {
  console.log('Usage: node render.js [template.html] [responses.json]');
}

var responses = JSON.parse(fs.readFileSync(process.argv[3], 'utf-8'));

var handlebars = require('handlebars');

var template = fs.readFileSync(process.argv[2], 'utf-8');

var renderer = handlebars.compile(template);

console.log(renderer({ responses: responses }));
