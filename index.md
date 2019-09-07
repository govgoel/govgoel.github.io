                                                         
                                              !!Welcome!!
                          
                         
                         
                         
<html>
<head>

<p><b>Enter the username you want to search</b></p>
<input type="text" id="user" placeholder="username">

<button onclick="myFunction()">Search</button>

<p><div id="Username"></div>
<p><div id = "noUser"></div>
<p><div id="Name"></div></br>
<p><div id="Bio"></div></br>
<p>
<p><div id="Avatar_named"></div><div>
<p><img id="Avatar" height="0" width="0"></img></p>
<p><div id="Identicon_named"></div>
<p><img id = "Identicon" height = "0" width = "0"></img></p>

<script>
                function myFunction() {
                var login = document.getElementById("user").value;
                var query = `query User($login: String!) {
                                user(login: $login) {
                                    login
                                    name
                                    avatarUrl
                                    bio
                                }
                            }`
                fetch('https://api.github.com/graphql', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                        'Accept': 'application/json',
                        'Authorization': 'bearer 3249bd7f85a30de1dc04e6f07cc8a877e45cdce8',
                    },
                    body: JSON.stringify({
                        query,
                        variables: { login },
                    })
                })

