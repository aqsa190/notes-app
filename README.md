<!DOCTYPE html>
<html>
<head>
  <title>Notes App</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f1f5f9;
      display: flex;
      justify-content: center;
      padding-top: 50px;
    }

    .box {
      background: white;
      width: 350px;
      padding: 25px;
      border-radius: 15px;
      box-shadow: 0 5px 20px rgba(0,0,0,0.1);
    }

    h1 {
      text-align: center;
    }

    textarea {
      width: 100%;
      height: 100px;
      padding: 10px;
      box-sizing: border-box;
      resize: none;
    }

    button {
      width: 100%;
      padding: 11px;
      margin-top: 10px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }

    .note {
      background: #f1f5f9;
      padding: 12px;
      margin-top: 10px;
      border-radius: 8px;
    }

    .delete {
      width: auto;
      padding: 6px 10px;
      margin-top: 8px;
    }
  </style>
</head>

<body>

  <div class="box">

    <h1>📝 Notes App</h1>

    <textarea id="noteInput" placeholder="Write your note..."></textarea>

    <button onclick="addNote()">Add Note</button>

    <div id="notes"></div>

  </div>

  <script>

    function addNote() {

      let noteText =
        document.getElementById("noteInput").value;

      if (noteText === "") {
        alert("Please write a note.");
        return;
      }

      let note =
        document.createElement("div");

      note.className = "note";

      note.innerHTML =
        noteText + "<br>";

      let deleteButton =
        document.createElement("button");

      deleteButton.className = "delete";

      deleteButton.textContent = "Delete";

      deleteButton.onclick = function() {
        note.remove();
      };

      note.appendChild(deleteButton);

      document.getElementById("notes")
        .appendChild(note);

      document.getElementById("noteInput").value = "";
    }

  </script>

</body>
</html>
