# HttpSession
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;
import java.io.IOException;

@WebServlet("/session-example")
public class SessionExampleServlet extends HttpServlet {

    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {

        // Get the session associated with the request, create a new one if it doesn't exist
        HttpSession session = request.getSession();

        // Set a session attribute
        session.setAttribute("username", "john_doe");

        // Get a session attribute
        String username = (String) session.getAttribute("username");

        response.setContentType("text/html");
        response.getWriter().println("Username from session: " + username);
    }
}
