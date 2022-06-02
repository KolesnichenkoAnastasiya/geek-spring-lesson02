1. В файл user.jsp добавила ссылку <th scope="row"><a href=' user/<%=(user.getId()).toString()%>'> <%= user.getId() %></a></th>;
2. В файл user_form.jsp добавила отображение имени usera 
     <% User user= (User) request.getAttribute("user"); { %>
     <input type="text" class="form-control" id="name" name="username" placeholder="Enter username" value="<%= user.getUsername() %>">
     <% } %>
3. В файл UserServlet.java добавила ссылку на файл user_form.jsp
     req.setAttribute("user", userRepository.findById(id));
     etServletContext().getRequestDispatcher("/user_form.jsp").forward(req, resp);
