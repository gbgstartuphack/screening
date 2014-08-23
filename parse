#!/usr/bin/env node

var fs = require('fs');

if (!fs.existsSync(process.argv[2])) {
  console.log('Usage: node parse.js [file.tsv]');
}

var fileContents = fs.readFileSync(process.argv[2], 'utf-8');

var lines = fileContents.split('\n');

var header = lines[0].trim().split('\t');

var responseLines = lines.slice(1);

var responses = responseLines.map(function(line) {
  var response = {};
  line.trim().split('\t').forEach(function(part, i) {
    if (header[i]) {
      response[header[i]] = part; 
    }
  });
  return response;
});

console.log(JSON.stringify(responses, null, 2));
