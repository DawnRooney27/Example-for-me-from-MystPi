<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Example</title>
    <style>
      body {
        margin: 0 auto;
        max-width: 50em;
        padding: 3em;
        font-family: sans-serif;
      }
    </style>
  </head>
  <body>
    <h1>
      Enter a project ID
    </h1>
    <input id="id">
    <button onclick="getData()">
      Submit
    </button>
    <p id="output"></p>
    <p>
      To view the code, right click this page then click view page source.
    </p>
    <script>
      function getData() {
        fetch ('https://scratchdb.lefty.one/v3/project/info/' + document.getElementById('id').value)
          .then(result => result.json())
          .then(result => {
            document.getElementById('output').innerText = result.statistics.views + ' views (note that this might not be entirely accurate, as ScratchDB is not always up-to-date)';
          });
      }
    </script>
  </body>
</html>
