# Beispiel:

### ELemente sichbar uns unsichtbar machen

### Im html:

   <script>
            function showLine(line) {
                var myLine = document.getElementById(line);
                myLine.className = "";
            }
            function removeLine(line) {
                var myLine = document.getElementById(line);
                myLine.className = "hidden";
            }
        </script>



<div class="hidden" id="div2">

   <div>
      <form name="res2" id="res2">
        <button onclick="showLine('div3'); return false" class="addButton" type ="Button" id="add2" >Add</button>
        <button onclick="removeLine('div2'); return false" class="removeButton" type ="Button" id="remove1">Remove</button>
    </form>
</div> 

### CSS:

.hidden{
    display: none;
}



## Navbar:

## Html:

<nav class="navbar">
            <ul>
                <li>
                    <a href="./DashboardPost.jsp">POST</a>
                </li>
                <li>
                    <a href="./DashboardGet.jsp">GET</a>
                </li>
            </ul>
        </nav>

## CSS:

.navbar{
    background-color: darkgreen;
}

.navbar ul{
    list-style-type: none;
}

.navbar li{
    display: inline;
    padding: 1%;
}

.navbar a{
    text-decoration: none;
    color: black;  
}