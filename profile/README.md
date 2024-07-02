## Introduction
ProntoGUI is a tool used by developers of back-end, service-orientented, embedded software, and similar kinds of software, to provide a Graphical User Interface (GUI) for themselves or end users to visualize, configure, and operate the software.

Traditionally, a GUI was developed using an immediate-mode library, a native application (App), or a web-based application.  Each of these approaches has its tradeoffs and ideal use cases.  The one thing they have in common is the moderate to large learning curve to be proficient at developing the application.  There is time wasting when context swithing between thinking like a back-end developer versus thinking like an App developer.  Initial results of how the app looks and feels is often a freshman take and substantial effort is needed to make it look nice.

Immediate-mode libraries, such as Qt, Gnome, or Windows Forms, render a GUI in the same process environment where the software runs.  Sometimes this isn't practical because the software is running in a headless scenario.  In this case, a GUI is developed as a traditional application in a separate project altogether using tools like React.js.  A networking connection provides a communication bridge to the back-end software.

ProntoGUI has two primary pieces:  a library and the app.  The library is built specificaly for each language and provides a data model and communication layer utilized by the back-end code.  The App is a native application built for either Winodows, Linux, or Mac OS, and functions similar to a web browser by rendering the GUI experience to the user.  The library communicates to the App using industry standard gRPC over an HTTP/2 connection.  

The data model begins with data structures called "primitives" that describe the informational and behavioral aspects of the user interface.  It purposefully omits fine-grained details like screen positioning, layout, colors, fonts, etc.  The goal of primitives is to describe the structural elements of what's shown on the screen from the back-end developer's perspective.

Some primitives act as "containers" that hold other primitives.  Containers can represent a table, a list of primitives, a set of GUI screens, and more.  

Next, there are data structures called "embodiments" that describe the shape each structural element takes on and how it looks and feels.  The back-end developer can configure embodiments using JSON.
