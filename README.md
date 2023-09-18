````html

<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>CSS Animation</title>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/highlight.min.js"></script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/languages/javascript.min.js"></script>
      <script>
         hljs.highlightAll();
      </script>
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
      <style>
      
         .response {
         border: 1px solid white;
         width: 90vw;
         margin: auto;
         position: relative;
         display: flex;
         flex-wrap: nowrap; /* Prevent wrapping of boxes when scrolling horizontally */
         margin-bottom: 20px;
         background: black;
         overflow-x: auto; /* Enable horizontal scrolling */
         border-radius: 10px;
         max-height: 40vh;
         color: white;
         padding-left: 14px;
         }
         
         
         .git{
         /*   for link  */
         display: block;
         width: 90%;
         color: white;
         margin: auto;
         border-radius: 40px;
         padding-top: 15px;
         text-decoration: none;
         height: 40px;
         text-align: center;
         margin-top: 30px;
         border: 1px solid white;
         }
         
         
         /* Styles for the copy button */
         .copy-button {
         position: sticky;
         top: 10px;
         right: 10px;
         height: 25px;
         padding: 4px 8px;
         border: none;
         border-radius: 4px;
         background-color: #007bff;
         color: #fff;
         cursor: pointer;
         }
         
      </style>
      
      <style>
      
         html {
         box-sizing: border-box;
         background: #000;
         color: white;
         }
         
        
         .accordion-button {
         margin: 20px;
         width: 85vw;
         border-radius: 50px;
         background-color: dodgerblue;
         color: white;
         border: none;
         height: 50px; /* Set a fixed height for the button */
         }
         
         
         .accordion-button:hover {
         background-color: saddlebrown;
         }
         
         
         .container {
         max-width: 100vw;
         overflow: hidden;
         transition: max-height 0.6s ease-out; /* Use max-height for smooth transition */
         }
         
         
         .container.closed {
         max-height: 0;
         }
         
      </style>
      
   </head>
   <body>
     
      <!--          start          -->



      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)"> Hilight.js viewer </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
   &lt;head&gt;
      &lt;meta charset="UTF-8"&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
      &lt;title&gt;Syntax Highlighting&lt;/title&gt;
      &lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.2.0/highlight.min.js"&gt;&lt;/script&gt;
      &lt;style&gt;
      
         *{
         box-sizing: border-box;
         margin: 0;
         }
         
         
         html{
         background: #000;
         }
         
         
         .fakeTextarea {
         outline: none;
         width: 100vw;
         background: #000;
         margin: auto;
         white-space: pre-wrap;
         overflow: auto;
         color: white;
         padding: 20px;
         height: 900px;
         }
         
         
         code {
         white-space: pre;
         overflow-wrap: normal;
         word-break: normal;
         }
         
         
      &lt;/style&gt;
   &lt;/head&gt;
   &lt;body&gt;
     
      &lt;div class="editor-container fakeTextarea" contenteditable="true" spellcheck="false"&gt;&lt;/div&gt;
      
      
      &lt;script&gt;
         hljs.initHighlightingOnLoad();
         
         const fakeTextareas = document.querySelectorAll('.fakeTextarea');
         
         // Add an input event listener with debounce to apply syntax highlighting
         fakeTextareas.forEach(textarea =&gt; {
             let debounceTimer;
             textarea.addEventListener('input', () =&gt; {
                 clearTimeout(debounceTimer);
                 debounceTimer = setTimeout(() =&gt; {
                     highlightCode(textarea);
                 }, 10); // Delay for 500ms after the last input
             });
         });
         
         // Function to apply syntax highlighting
         function highlightCode(textarea) {
             const codeContent = textarea.innerText;
             textarea.innerHTML = `&lt;code&gt;${hljs.highlightAuto(codeContent).value}&lt;/code&gt;`;
         }
      &lt;/script&gt;
      
      
   &lt;/body&gt;
&lt;/html&gt;
                 

               </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
            <br>
         </div>
      </div>
      
       <!--           end           -->
     
      
      

   
   
   
         <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">  Copy by click with copyable class  </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;script&gt;
   document.addEventListener('click', (event) =&gt; {
    if (event.target.classList.contains('copyable')) {
        const temp = document.createElement('textarea');
        temp.value = event.target.textContent;
        document.body.appendChild(temp);
        temp.select();
        document.execCommand('copy');
        document.body.removeChild(temp);
   
        // Add CSS styles directly to the element
        event.target.style.cssText = 'opacity: 0.5; color: red; border: none;';
   
        // Reset the styles after 1 second
        setTimeout(() =&gt; {
            event.target.style.cssText = ''; // Reset all styles
          
        }, 1000);
    }
   });
&lt;/script&gt;
          
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)"> Copy by long peess  by longcopy class </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;script&gt;
   let longPress = false;
   let pressTimer;
   
   // Add a touchstart event listener for copying text on long-press
   document.addEventListener('touchstart', (event) =&gt; {
       if (event.target.classList.contains('longcopy')) {
           pressTimer = setTimeout(() =&gt; {
               const temp = document.createElement('textarea');
               temp.value = event.target.textContent;
               document.body.appendChild(temp);
               temp.select();
               document.execCommand('copy');
               document.body.removeChild(temp);
   
               // Prevent the default context menu and text selection
               event.preventDefault();
   
               // Add CSS styles directly to the element
               event.target.style.cssText = 'opacity: 0.5; color: red; border: none;';
   
               // Reset the styles after 1 second
               setTimeout(() =&gt; {
                   event.target.style.cssText = ''; // Reset all styles
               }, 1000);
           }, 1000); // Adjust the time (in milliseconds) for long-press
       }
   });
   
   // Add a touchend event listener to clear the timer
   document.addEventListener('touchend', (event) =&gt; {
       clearTimeout(pressTimer);
   });
&lt;/script&gt;
          
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
       <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">  Accordion   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
   &lt;head&gt;
      &lt;meta charset="UTF-8"&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
      &lt;title&gt;CSS Animation&lt;/title&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/highlight.min.js"&gt;&lt;/script&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/languages/javascript.min.js"&gt;&lt;/script&gt;
      &lt;script&gt;
         hljs.highlightAll();
      &lt;/script&gt;
      &lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&gt;
      &lt;style&gt;
      
         .response {
         border: 1px solid white;
         width: 90vw;
         margin: auto;
         position: relative;
         display: flex;
         flex-wrap: nowrap; /* Prevent wrapping of boxes when scrolling horizontally */
         margin-bottom: 20px;
         background: black;
         overflow-x: auto; /* Enable horizontal scrolling */
         border-radius: 10px;
         max-height: 40vh;
         color: white;
         padding-left: 14px;
         }
         
         
         .git{
         /*   for link  */
         display: block;
         width: 90%;
         color: white;
         margin: auto;
         border-radius: 40px;
         padding-top: 15px;
         text-decoration: none;
         height: 40px;
         text-align: center;
         margin-top: 30px;
         border: 1px solid white;
         }
         
         
         /* Styles for the copy button */
         .copy-button {
         position: sticky;
         top: 10px;
         right: 10px;
         height: 25px;
         padding: 4px 8px;
         border: none;
         border-radius: 4px;
         background-color: #007bff;
         color: #fff;
         cursor: pointer;
         }
         
      &lt;/style&gt;
      
      &lt;style&gt;
      
         html {
         box-sizing: border-box;
         background: #000;
         color: white;
         }
         
        
         .accordion-button {
         margin: 20px;
         width: 85vw;
         border-radius: 50px;
         background-color: dodgerblue;
         color: white;
         border: none;
         height: 50px; /* Set a fixed height for the button */
         }
         
         
         .accordion-button:hover {
         background-color: saddlebrown;
         }
         
         
         .container {
         max-width: 100vw;
         overflow: hidden;
         transition: max-height 0.6s ease-out; /* Use max-height for smooth transition */
         }
         
         
         .container.closed {
         max-height: 0;
         }
         
      &lt;/style&gt;
      
   &lt;/head&gt;
   &lt;body&gt;
     
      &lt;!--          start          --&gt;



      &lt;div class="accordion"&gt;
         &lt;button class="accordion-button" onclick="toggleContainer(this)"&gt;Box&lt;/button&gt;
         &lt;div class="container closed"&gt;
            &lt;div class="response"&gt;
               &lt;pre&gt;&lt;code style="background: black;" class="language-html"&gt;
                 

               &lt;/code&gt;&lt;/pre&gt;
               &lt;button class="copy-button"&gt;Copy.    &lt;/button&gt;
            &lt;/div&gt;
            &lt;br&gt;
            &lt;br&gt;
         &lt;/div&gt;
      &lt;/div&gt;
      
       &lt;!--           end           --&gt;
     
      
      
      
      
      
      
      
      &lt;!--          start          --&gt;

      
      
      &lt;div class="accordion"&gt;
         &lt;button class="accordion-button" onclick="toggleContainer(this)"&gt;Simple&lt;/button&gt;
         &lt;div class="container closed"&gt;
            &lt;p&gt;This is some content inside the first container.&lt;/p&gt;
            &lt;pre&gt;
                .
                .
                .
            &lt;/pre&gt;
         &lt;/div&gt;
      &lt;/div&gt;
      
      
      &lt;!--           end           --&gt;








      
      
      &lt;!--          start          --&gt;
      
      
      
      &lt;div class="accordion"&gt;
         &lt;button class="accordion-button" onclick="toggleContainer(this)"&gt;Link&lt;/button&gt;
         &lt;div class="container closed"&gt;
            &lt;a href="" class="git"&gt;link 1&lt;/a&gt;
            &lt;a href="" class="git"&gt;link 2&lt;/a&gt;
         &lt;/div&gt;
      &lt;/div&gt;
      
      
      
            &lt;!--           end           --&gt;









      &lt;!-- 
         **********************
         iske phle sb Krna hai 
         
         **********************
         
         
         --&gt;    
      &lt;div style="height: 50vh;" &gt;&lt;/div&gt;
      &lt;script&gt;
         function toggleContainer(button) {
             const container = button.nextElementSibling;
             const isOpen = !container.classList.contains('closed');
         
             if (isOpen) {
                 // Container is open, so just close it without scrolling
                 container.style.maxHeight = '0';
                 container.classList.add('closed');
             } else {
                 // Calculate the container's current scroll height before opening
                 const currentScrollHeight = container.scrollHeight;
         
                 // Open the container
                 container.style.maxHeight = currentScrollHeight + 'px';
                 container.classList.remove('closed');
             }
         }
         
         
             
      &lt;/script&gt;
      &lt;script&gt;
         function copyResponseText() {
           const responseTextElement = this.previousElementSibling;
           const textToCopy = responseTextElement.innerText;
         
          
           const tempTextArea = document.createElement('textarea');
           tempTextArea.value = textToCopy;
           document.body.appendChild(tempTextArea);
         
         
           tempTextArea.select();
           document.execCommand('copy');
         
           
           document.body.removeChild(tempTextArea);
         
         
           this.innerText = 'Copied!';
           setTimeout(() =&gt; {
             this.innerText = 'Copy';
           }, 2000);
         }
         
         
         const copyButtons = document.querySelectorAll('.copy-button');
         copyButtons.forEach((button) =&gt; {
           button.addEventListener('click', copyResponseText);
         });
      &lt;/script&gt;
   &lt;/body&gt;
&lt;/html&gt;
 
   
                
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
       <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   Escape code   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
  &lt;meta charset="UTF-8"&gt;
  &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
  &lt;title&gt;HTML Escape and Format Code&lt;/title&gt;
  &lt;style&gt;
    #box {
      border: 1px solid white;
      width: 90vw;
      margin: auto;
      position: relative;
      display: flex;
      flex-wrap: nowrap; /* Prevent wrapping of boxes when scrolling horizontally */
      margin-bottom: 20px;
      background: black;
      overflow-x: auto; /* Enable horizontal scrolling */
      border-radius: 10px;
      height: 400px;
      color: white;
      outline: none;
      padding-left: 14px;
    }
  &lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
  &lt;textarea class="response" id="box" wrap="off" placeholder="Enter your text here"&gt;&lt;/textarea&gt;
    &lt;button id="formatButton" onclick="formatAndCopy()"&gt;Format and Copy&lt;/button&gt;

  &lt;button id="escapeButton" onclick="escapeAndCopy()"&gt;Escape and Copy&lt;/button&gt;
  &lt;button id="resetButton" onclick="resetInput()"&gt;Reset&lt;/button&gt;

  &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/js-beautify/1.13.0/beautify-html.min.js"&gt;&lt;/script&gt;

  &lt;script&gt;
    const prettierPlugins = {
      html: window.htmlPrettier
    };

    prettier.init({ plugins: [window.htmlPrettier] });

    function escapeAndCopy() {
      const box = document.getElementById("box");
      const escapedCode = htmlEscape(box.value);
      box.value = escapedCode;
      copyToClipboard(escapedCode);
    }

    function formatAndCopy() {
      const box = document.getElementById("box");
      const currentText = box.value;
      const formattedText = formatWithJsBeautify(currentText);
      box.value = formattedText;
      copyToClipboard(formattedText);
    }

    function htmlEscape(text) {
      return text.replace(/[&lt;&gt;&amp;]/g, function (tag) {
        const replacements = {
          '&lt;': '&amp;lt;',
          '&gt;': '&amp;gt;',
          '&amp;': '&amp;amp;'
        };
        return replacements[tag] || tag;
      });
    }

    function copyToClipboard(text) {
      const el = document.createElement("textarea");
      el.value = text;
      document.body.appendChild(el);
      el.select();
      document.execCommand("copy");
      document.body.removeChild(el);
    }

    function resetInput() {
      const box = document.getElementById("box");
      box.value = '';
      box.style.overflowX = 'auto'; // Reset horizontal scrollbar to auto
    }

    function formatWithJsBeautify(text) {
      try {
        return html_beautify(text, {
          indent_size: 3, // Set the desired indent size (3 spaces per level)
          wrap_line_length: 0 // Do not wrap lines
        });
      } catch (error) {
        console.error("Formatting error:", error);
        return text; // Return the original text in case of an error
      }
    }
  &lt;/script&gt;
&lt;/body&gt;
&lt;/html&gt;

 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
       <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   Combine html css js   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
    &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
    &lt;title&gt;Faster Syntax Highlighting&lt;/title&gt;
    &lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&gt;
    &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.2.0/highlight.min.js"&gt;&lt;/script&gt;
    &lt;style&gt;
    *{
      margin: 0;
      background: #000;
    }
        .editor-container {
            border: 0.1px dotted #ccc;
            padding: 10px;
            width: 80vw;
            min-height: 60px; /* Changed to min-height */
            font-family: monospace;
            white-space: pre-wrap;
            overflow: auto;
            background: black;
            color: white;
            margin: auto;
            line-height: 1.5;
            
            outline: none;
        }

        code {
          line-height: 1.5;
            white-space: pre;
            overflow-wrap: normal;
            word-break: normal;
        }
    &lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
  &lt;button class="copy-button" style="position: sticky; top: 50vh; left: 90vw; height: 25px; padding: 4px 8px; border: none; background-color: #007bff; color: #fff; cursor: pointer;" onclick="copyBodyText(this)"&gt;Copy combined code&lt;/button&gt;
  
  &lt;pre&gt;&lt;code class="language-html" style="background: black;"&gt;&amp;lt;!DOCTYPE html&amp;gt;
&amp;lt;html lang=&amp;quot;en&amp;quot;&amp;gt;
&amp;lt;head&amp;gt;
  &amp;lt;meta charset=&amp;quot;UTF-8&amp;quot;&amp;gt;
  &amp;lt;meta name=&amp;quot;viewport&amp;quot; content=&amp;quot;width=device-width, initial-scale=1.0&amp;quot;&amp;gt;
  &amp;lt;meta http-equiv=&amp;quot;X-UA-Compatible&amp;quot; content=&amp;quot;ie=edge&amp;quot;&amp;gt;
  &amp;lt;title&amp;gt;Document&amp;lt;/title&amp;gt;
  &amp;lt;style&amp;gt;
  &lt;span&gt; /* enter css */&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
    &lt;div class="editor-container fakeTextarea" contenteditable="true" spellcheck="false"&gt;&lt;/div&gt;
&lt;pre&gt;&lt;code class="language-html" style="background: black;"&gt;&amp;lt;/style&amp;gt;
&amp;lt;/head&amp;gt;
&amp;lt;body&amp;gt;
&lt;span&gt;&amp;lt;!-- Enter html of body tag --&amp;gt;&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
    &lt;div class="editor-container fakeTextarea" contenteditable="true" spellcheck="false"&gt;&lt;/div&gt;
    &lt;pre&gt;&lt;code class="language-html" style="background: black;"&gt;&amp;lt;script&amp;gt;
&lt;span&gt;//Enter javascript&lt;/span&gt;
&lt;/code&gt;&lt;/pre&gt;
    &lt;div class="editor-container fakeTextarea" contenteditable="true" spellcheck="false"&gt;&lt;/div&gt;
  &lt;pre&gt;&lt;code class="language-html" style="background: black;"&gt;
&amp;lt;/script&amp;gt;
&amp;lt;/body&amp;gt;
&amp;lt;/html&amp;gt;
&lt;/code&gt;&lt;/pre&gt;
    &lt;script&gt;
        const fakeTextareas = document.querySelectorAll('.fakeTextarea');

        // Highlight and format the code when the user finishes editing
        fakeTextareas.forEach(textarea =&gt; {
            textarea.addEventListener('input', () =&gt; {
                clearTimeout(textarea.formatTimeout);
                textarea.formatTimeout = setTimeout(() =&gt; formatAndHighlightCode(textarea), 500); // Delay for 500ms after the last input
            });
        });

        function formatAndHighlightCode(textarea) {
            const codeContent = textarea.innerText;
            const formattedCode = formatSourceCode(codeContent);
            textarea.innerHTML = `&lt;code&gt;${hljs.highlightAuto(formattedCode).value}&lt;/code&gt;`;
        }

        function formatSourceCode(code) {
            const tabSize = 2;
            const lines = code.split('\n');
            let formattedCode = '';
            let indent = 0;

            lines.forEach((line, index) =&gt; {
                line = line.trim();

                if (line.endsWith('}')) {
                    indent -= tabSize;
                }

                formattedCode += ' '.repeat(indent) + line + '\n';

                if (line.endsWith('{')) {
                    indent += tabSize;
                }
            });

            return formattedCode.trim();
        }

        // Call formatAndHighlightCode initially to apply formatting and syntax highlighting to any initial content in the textareas
        fakeTextareas.forEach(textarea =&gt; formatAndHighlightCode(textarea));
    &lt;/script&gt;
    &lt;script&gt;
    hljs.highlightAll();
&lt;/script&gt;
&lt;script&gt;
    function copyBodyText(button) {
      const bodyText = document.body.innerText;

      const tempTextArea = document.createElement('textarea');
      tempTextArea.value = bodyText;
      document.body.appendChild(tempTextArea);

      tempTextArea.select();
      document.execCommand('copy');

      document.body.removeChild(tempTextArea);

      button.innerText = 'Copied!';
      setTimeout(() =&gt; {
        button.innerText = 'Copy Body Text';
      }, 2000);
    }
  &lt;/script&gt;
  
  
  &lt;!-- for hide button --&gt;
  
  
  &lt;script&gt;
    function copyBodyText(button) {
      button.style.display = 'none'; // Hide the button

      const bodyText = document.body.innerText;

      const tempTextArea = document.createElement('textarea');
      tempTextArea.value = bodyText;
      document.body.appendChild(tempTextArea);

      tempTextArea.select();
      document.execCommand('copy');

      document.body.removeChild(tempTextArea);

      setTimeout(() =&gt; {
        button.style.display = 'inline-block'; // Show the button after 2 seconds
        button.innerText = 'Copied!';
        setTimeout(() =&gt; {
          button.innerText = 'Copy combined code';
        }, 2000);
      }, 2);
    }
  &lt;/script&gt;
&lt;/body&gt;
&lt;/html&gt;

 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
       <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   Inspect in chrome by bookmark   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">javascript:(function () { var script = document.createElement('script'); script.src="//cdn.jsdelivr.net/npm/eruda"; document.body.appendChild(script); script.onload = function () { eruda.init() } })();</code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">  Github, replit, Google drive and YouTube    </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html&gt;
   &lt;head&gt;
      &lt;meta charset="UTF-8"&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
      &lt;meta http-equiv="X-UA-Compatible" content="ie=edge"&gt;
      &lt;title&gt;Link Converter&lt;/title&gt;
      &lt;title&gt;Link Converter&lt;/title&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/2.0.8/clipboard.min.js"&gt;&lt;/script&gt;
      &lt;style&gt;
         
         body {
         font-family: Arial, sans-serif;
         text-align: center;
         margin: 0 20px; /* Equal margin from left and right */
         }
         
         
         h1 {
         margin-top: 20px;
         }
         
         
         
         label, input[type="text"], button, #outputLink, p {
         margin: 10px 0;
         }
         
         
         input[type="text"] {
         width: 90%;
         padding: 10px;
         font-size: 14px;
         }
         
         
         button {
         padding: 10px 20px;
         background-color: #007bff;
         color: white;
         border: none;
         cursor: pointer;
         }
         
         
         #outputLink a {
         color: #007bff;
         text-decoration: none;
         }
         
      &lt;/style&gt;
      
   &lt;/head&gt;
   &lt;body&gt;
     
      &lt;h1&gt;Link Converter&lt;/h1&gt;
      &lt;input type="text" id="linkInput" placeholder="Paste Repl.it, GitHub, Google Drive, or YouTube link"&gt;
      &lt;button id="convertButton"&gt;Convert&lt;/button&gt;
      &lt;div id="outputLink"&gt;&lt;/div&gt;
      
      
      &lt;script&gt;
         // Function to convert a Google Drive link to the desired format
         function convertDriveLink(originalLink) {
             const fileIdRegex = /\/d\/([^/]+)/;
             const match = originalLink.match(fileIdRegex);
         
             if (match) {
                 const fileId = match[1];
                 const directDownloadLink = `https://drive.google.com/uc?id=${fileId}&amp;export=download`;
                 return directDownloadLink;
             } else {
                 return "Invalid Google Drive link";
             }
         }
         
         // Function to perform the link conversion
         function convertLink(link) {
             const linkInput = document.getElementById('linkInput');
             const outputLinkContainer = document.getElementById('outputLink');
         
             if (link.includes("drive.google.com")) {
                 // Handle Google Drive link conversion
                 const driveText = convertDriveLink(link);
                 if (driveText === "Invalid Google Drive link") {
                     outputLinkContainer.innerHTML = "Invalid link";
                 } else {
                     // Display the converted link on the webpage with blue text color
                     outputLinkContainer.innerHTML = `Converted Google Drive Link: &lt;span id="driveLink" style="color: blue;"&gt;${driveText}&lt;/span&gt;`;
                     const clipboard = new ClipboardJS('#driveLink', {
                         text: function () {
                             return driveText;
                         }
                     });
                     clipboard.on('success', function (e) {
                         // Clear the selection after copying
                         e.clearSelection();
                     });
                 }
                 linkInput.value = ''; // Clear the input field
             } else if (link.includes("youtube.com") || link.includes("youtu.be")) {
                 // Handle YouTube link conversion
                 const youtubePattern = /(?:https?:\/\/)?(?:www\.)?(?:youtube\.com\/(?:watch\?v=|shorts\/|live\/|embed\/|v\/)|youtu\.be\/)([^&amp;?/]+)/i;
                 const youtubeMatch = link.match(youtubePattern);
         
                 if (youtubeMatch) {
                     const videoId = youtubeMatch[1];
                     const videoLink = `https://ytload.com/en/download/${videoId}/mp4_18/`;
                     const audioLink = `https://ytload.com/en/download/${videoId}/mp3_128/`;
         
                     outputLinkContainer.innerHTML = `
                         Video: &lt;a href="${videoLink}" target="_blank"&gt;${videoLink}&lt;/a&gt;&lt;br&gt;
                         Audio: &lt;a href="${audioLink}" target="_blank"&gt;${audioLink}&lt;/a&gt;
                     `;
                     linkInput.value = ''; // Clear the input field
                 } else {
                     outputLinkContainer.innerHTML = "Invalid YouTube link format.";
                     linkInput.value = ''; // Clear the input field
                 }
             } else {
                 // Handle Replit and GitHub link conversion
                 const replitPattern = /https:\/\/replit\.com\/@[^/]+\/([^/]+)(?:\?.*)?#([^?]+)/;
                 const githubPattern = /github\.com\/([^/]+)\/([^/]+)\/blob\/main\/(.+)/i;
                 const replitMatch = link.match(replitPattern);
                 const githubMatch = link.match(githubPattern);
         
                 if (replitMatch) {
                     const placeholder = replitMatch[1];
                     let path = replitMatch[2];
                     const username = link.match(/https:\/\/replit\.com\/@([^/]+)/)[1];
                     if (path.endsWith("index.html")) {
                         path = path.substring(0, path.length - 10); // Remove "index.html"
                     }
                     const alternateLink = `${placeholder}.${username}.repl.co/${path}`;
                     const fullAlternateLink = "https://" + alternateLink.replace(/\?v=\d+/, "");
                     outputLinkContainer.innerHTML = `Converted Replit link: &lt;a href="${fullAlternateLink}" target="_blank"&gt;${fullAlternateLink}&lt;/a&gt;`;
                     linkInput.value = ''; // Clear the input field
                 } else if (githubMatch) {
                     const username = githubMatch[1];
                     const repo = githubMatch[2];
                     let path = githubMatch[3];
                     if (path.endsWith("index.html")) {
                         path = path.substring(0, path.length - 10); // Remove "index.html"
                     }
                     if (repo.toLowerCase() === `${username}.github.io`) {
                         outputLinkContainer.innerHTML = `Converted GitHub Link: &lt;a href="https://${username}.github.io/${path}" target="_blank"&gt;https://${username}.github.io/${path}&lt;/a&gt;`;
                     } else {
                         const outputLink = `https://${username}.github.io/${repo}/${path}`;
                         outputLinkContainer.innerHTML = `Converted GitHub Link: &lt;a href="${outputLink}" target="_blank"&gt;${outputLink}&lt;/a&gt;`;
                     }
                     linkInput.value = ''; // Clear the input field
                 } else {
                     outputLinkContainer.innerHTML = "Invalid link format.";
                     linkInput.value = ''; // Clear the input field
                 }
             }
         }
         
         // Add event listeners for the input field to detect changes and pasted content
         document.getElementById("linkInput").addEventListener("input", function () {
             const linkInput = document.getElementById('linkInput');
             const link = linkInput.value;
         
             // Automatically trigger the "Convert" button if a YouTube or Google Drive link is detected
             if (link.includes("youtube.com") || link.includes("youtu.be") || link.includes("drive.google.com")) {
                 document.getElementById("convertButton").click();
             }
         });
         
         // Add an event listener for the "Convert" button
         document.getElementById("convertButton").addEventListener("click", function () {
             const linkInput = document.getElementById('linkInput');
             const link = linkInput.value;
             convertLink(link);
         });
         
      &lt;/script&gt;
      
      
   &lt;/body&gt;
&lt;/html&gt;
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
       <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   Web clone by me   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
   &lt;head&gt;
      &lt;meta charset="UTF-8"&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
      &lt;meta http-equiv="X-UA-Compatible" content="ie=edge"&gt;
      &lt;title&gt;Document&lt;/title&gt;
      &lt;style&gt;
         *
         {
         padding-right: 5px;
         padding-left: 5px;
         color: white;
         }
         body
         {
         background: black;
         }
         #ytr{
         padding: 0px;
         text-decoration: underline;
         color: deepskyblue;
         }
         #pro{
         width: 100%;
         background: black;
         height:45px;
         font-size: 20px;
         padding-top: 20px;
         position: fixed;
         top: 0px;
         left: 0px;
         border-bottom: 1px solid  #323441;
         }
         ul{
         padding-left: 50px;
         line-height: 30px;
         }
         a
         {
         padding-right: 80px;
         color: white;
         text-decoration: none;
         }
         h1
         {
         margin-top:50px;
         margin-bottom: 40px;
         border-bottom: 1px solid   #323441;
         padding-bottom: 6px;
         }
         p{
         line-height: 30px;
         }
      &lt;/style&gt;
   &lt;/head&gt;
   &lt;body&gt;
      &lt;div id="pro"&gt;
         &lt;div&gt;
            &lt;a href="https://urluploader.vercel.app/"&gt;All url upload&lt;/a&gt;
            &lt;a href=""&gt;©&lt;/a&gt;
            &lt;a href=""&gt;&lt;/a&gt;
         &lt;/div&gt;
      &lt;/div&gt;
      &lt;p
         style="padding-top: 80px"
         &gt;introduction&lt;/p&gt;
      &lt;h1
         style="margin-top: 20px;
         "
         &gt;All Url Uploader&lt;/h1&gt;
      &lt;p style="line-height: 29px;
         margin-top: 50px;"&gt;A simple Telegram bot, upload media file | video to Telegram using the direct download link.&lt;/p&gt;
      &lt;h1 style="margin-top: 50px;
         "&gt;Introduction&lt;/h1&gt;
      &lt;ul &gt;
         &lt;li&gt;     Youtube, Google Drive, Apple Music, Spotify, Resso, &amp; Direct Links support.  &lt;/li&gt;
         &lt;li&gt;      Bot Can upload document, video &amp; audio types. &lt;/li&gt;
         &lt;li&gt;      Deploy To Heroku | locally | VPS | Digital Ocean | Koyeb | Render. &lt;/li&gt;
         &lt;li&gt;     Custom thumbnail support.  &lt;/li&gt;
      &lt;/ul&gt;
      &lt;h1&gt;Commands&lt;/h1&gt;
      &lt;ul&gt;
         &lt;li&gt;    /start - Start the Bot &lt;/li&gt;
         &lt;li&gt;   /about - About the Bot  &lt;/li&gt;
         &lt;li&gt;   /help - Introduction to use url uploader bot  &lt;/li&gt;
         &lt;li&gt;   /thumb - view your custom thumbnail
            /delthumb - delete your custom thumbnail  
         &lt;/li&gt;
         &lt;li&gt;   /delthumb - delete your custom thumbnail  &lt;/li&gt;
         &lt;li&gt;   /thumb - Add custom thumbnail to your uploaded file ( send thumbnail and reply /thumb to it)  &lt;/li&gt;
         &lt;li&gt;    /delthumb - To Delete your custom thumbnail &lt;/li&gt;
      &lt;/ul&gt;
      &lt;h1&gt;Ask Questions &lt;/h1&gt;
      &lt;p&gt;For questions and support please use
         &lt;span 
            &gt;&lt;a id="ytr" style="
            "
            href="https://www.block-disposable-email.com/cms/"&gt;Discussions&lt;/a&gt;&lt;/span&gt;. The issue list of this repo is exclusively for bug reports and feature requests.
      &lt;/p&gt;
      &lt;h1&gt;Founds Bugs?&lt;/h1&gt;
      &lt;p style="
         margin-bottom: 60px;
         border-bottom: 1px solid  #323441;
         padding-bottom: 90px;
         "&gt;Make sure to read the Issue Reporting Checklist. before opening an issue. Issues not conforming to the guidelines may be closed immediately.&lt;/p&gt;
      &lt;p style="text-align: right;
         font-weight: 300;
         font-size: 20px;
         padding-bottom: 50px;
         "&gt;
         Change Logs &gt;
      &lt;/p&gt;
   &lt;/body&gt;
&lt;/html&gt;
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
 
   
                      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">Animated bots      </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
   &lt;head&gt;
      &lt;meta charset="UTF-8"&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
      &lt;meta http-equiv="X-UA-Compatible" content="ie=edge"&gt;
      &lt;title&gt;Document&lt;/title&gt;
      &lt;link rel="stylesheet" href="https://unpkg.com/aos@next/dist/aos.css" /&gt;
      &lt;style&gt;
         *
         {
         text-decoration: none;
         color: white;
         }
         body
         {
         background: black;
         padding-left: 15px;
         }
         #ytr{
         padding: 0px;
         text-decoration: underline;
         color: deepskyblue;
         }
         div{
         line-height: 29px;
         }
         #pro{
         width: 100%;
         background: black;
         height:45px;
         font-size: 20px;
         padding-top: 20px;
         position: fixed;
         top: 0px;
         left: 0px;
         z-index: 2;
         border-bottom: 1px solid  #323441;
         }
         ul{
         padding-left: 35px;
         line-height: 30px;
         }
         .popular
         {
         padding-right: 80px;
         color: white;
         text-decoration: none;
         }
         h1
         {
         margin-top:80px;
         margin-bottom: 40px;
         border-bottom: 1px solid   #323441;
         padding-bottom: 6px;
         }
         p{
         line-height: 30px;
         padding: 0px
         }
      &lt;/style&gt;
   &lt;/head&gt;
   &lt;body&gt;
      &lt;div id="pro"&gt;
         &lt;div data-aos="zoom-in" data-aos-offset="200" data-aos-delay="70" data-aos-duration="1000" style="padding-left: 150px"&gt;
            &lt;a href=""&gt;Bots lists&lt;/a&gt;
         &lt;/div&gt;
      &lt;/div&gt;
      &lt;div&gt;
         &lt;p style="padding-top: 80px"&gt;introduction&lt;/p&gt;
         &lt;div data-aos="fade-right" data-aos-offset="20" data-aos-delay="70" data-aos-duration="1000"&gt;
            &lt;h1 style="margin-top: 20px;
               "&gt;&lt;a href="https://t.me/AnyDLBot"&gt;All url uploader 🔗&lt;/a&gt;&lt;/h1&gt;
            &lt;p style="line-height: 29px;
               margin-top: 50px;"&gt;A simple Telegram bot, upload media file | video to Telegram using the direct download link.&lt;/p&gt;
         &lt;/div&gt;
         &lt;div data-aos="fade-left" data-aos-offset="20" data-aos-delay="70" data-aos-duration="1000"&gt;
            &lt;h1&gt;&lt;a href="https://t.me/MKN_Hyper_renameBOT"&gt;File Renamer 🔗&lt;/a&gt;&lt;/h1&gt;
            It give you video of file at 5 min and also give you 6-9 screenshot if you set it settings
            &lt;ul 
            &lt;li&gt; &lt;a href="https://t.me/Pyro_Rename_Bot"&gt;Another renameBOT 🔗&lt;/a&gt; &lt;/li&gt;
            &lt;!--   &lt;li&gt;      Deploy To Heroku | locally | VPS | Digital Ocean | Koyeb | Render. &lt;/li&gt;
               &lt;li&gt;     Custom thumbnail support.  &lt;/li&gt; --&gt;
            &lt;/ul&gt;
         &lt;/div&gt;
         &lt;div data-aos="fade-down" data-aos-offset="400" data-aos-delay="70" data-aos-duration="1000"&gt;
            &lt;h1&gt; &lt;a href="https://T.me/DirectLinkGenerator_Bot"&gt;File to link bot 🔗&lt;/a&gt;&lt;/h1&gt;
            &lt;ul&gt;
               &lt;li&gt; &lt;a href="https://t.me/MKN_FtoL_BOT"&gt;Another bot 🔗&lt;/a&gt;&lt;/li&gt;
               &lt;!--   &lt;li&gt;   /about - About the Bot  &lt;/li&gt;
                  &lt;li&gt;   /help - Introduction to use url uploader bot  &lt;/li&gt;
                  &lt;li&gt;   /thumb - view your custom thumbnail
                  /delthumb - delete your custom thumbnail  &lt;/li&gt;
                  &lt;li&gt;   /delthumb - delete your custom thumbnail  &lt;/li&gt;
                  &lt;li&gt;   /thumb - Add custom thumbnail to your uploaded file ( send thumbnail and reply /thumb to it)  &lt;/li&gt;
                  &lt;li&gt;    /delthumb - To Delete your custom thumbnail &lt;/li&gt; --&gt;
               &lt;li&gt;&lt;a href="https://t.me/Telly_FileToLink_bot"&gt;Another 🔗&lt;/a&gt;&lt;/li&gt;
            &lt;/ul&gt;
            This can generate link but link valid only for 24 hours
            &lt;ul&gt;
               &lt;li&gt; &lt;a href="https://t.me/HHTGFilezDLBot"&gt;🔗&lt;/a&gt;&lt;/li&gt;
            &lt;/ul&gt;
         &lt;/div&gt;
         &lt;div data-aos="zoom-in" data-aos-offset="300" data-aos-delay="70" data-aos-duration="1000"&gt;
            &lt;h1&gt;&lt;a href="https://t.me/TellyLinkBypasser_bot"&gt;Links bypass bot 🔗&lt;/a&gt;&lt;/h1&gt;
            This bot can bypass any annoying short urls which show so much ads.
         &lt;/div&gt;
         &lt;div data-aos="fade-up" data-aos-offset="400" data-aos-delay="70" data-aos-duration="1000"&gt;
            &lt;h1 style="
               font-size: 30px;
               "&gt;&lt;a href="https://t.me/link_changer_omi_bot"&gt;PW link changer bot 🔗&lt;/a&gt;&lt;/h1&gt;
            &lt;p style="
               margin-bottom: 60px;
               border-bottom: 1px solid  #323441;
               padding-bottom: 90px;
               "&gt;This bot can change pw links in different pixals which is obtained thorough &lt;a style="color: red;" href="https://shrtco.de/AUq5at"&gt;web inspector pro &lt;/a&gt; (password:pa) application.&lt;/p&gt;
         &lt;/div&gt;
         &lt;!-- &lt;h1&gt;Founds Bugs?&lt;/h1&gt;
            &lt;p style="
            
            margin-bottom: 60px;
            border-bottom: 1px solid  #323441;
            padding-bottom: 90px;
            "&gt;Make sure to read the Issue Reporting Checklist. before opening an issue. Issues not conforming to the guidelines may be closed immediately.&lt;/p&gt;
             --&gt;
         &lt;p style="text-align: right;
            font-weight: 300;
            font-size: 20px;
            padding-bottom: 50px;
            "&gt;
            Change Logs &gt;
         &lt;/p&gt;
      &lt;/div&gt;
      &lt;script src="https://unpkg.com/aos@next/dist/aos.js"&gt;&lt;/script&gt;
      &lt;script&gt;
         AOS.init();
      &lt;/script&gt;
   &lt;/body&gt;
&lt;/html&gt;
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   Escape by hilight.js (not applicable)   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
   &lt;head&gt;
      &lt;meta charset="UTF-8"&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
      &lt;title&gt;Fake Syntax Highlighting&lt;/title&gt;
      &lt;!-- Include highlight.js library --&gt;
      &lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.2.0/highlight.min.js"&gt;&lt;/script&gt;
      &lt;style&gt;
         .editor-container {
         border: 1px solid #ccc;
         padding: 10px;
         width: 100vw;
         height: 130vw;
         font-family: monospace;
         white-space: pre-wrap;
         overflow: auto;
         background: black;
         color: white;
         margin: auto;
         }
         button {
         position: absolute;
         top: 50%;
         right: 10px; /* Adjust the right property for spacing between buttons */
         transform: translateY(-50%);
         }
         button:nth-child(2) {
         top: calc(50% - 50px); /* Adjust the vertical spacing */
         }
         button:nth-child(3) {
         top: calc(50% - 100px); /* Adjust the vertical spacing */
         }
         .editor {
         outline: none;
         }
         code {
         white-space: pre;
         overflow-wrap: normal;
         word-break: normal;
         }
         .escape-btn {
         margin-top: 10px;
         padding: 5px 10px;
         background: #007bff;
         color: white;
         border: none;
         cursor: pointer;
         }
      &lt;/style&gt;
   &lt;/head&gt;
   &lt;body&gt;
      &lt;div class="editor-container" contenteditable="true" id="fakeTextarea" spellcheck="false" oninput="highlightCode()"&gt;&lt;/div&gt;
      &lt;button class="escape-btn" onclick="escapeCode()"&gt;Escape&lt;/button&gt;
      &lt;button class="escape-btn" onclick="formatCode()"&gt;Format&lt;/button&gt;
      &lt;button class="escape-btn" onclick="resetInput()"&gt;Reset&lt;/button&gt;
      &lt;script&gt;
         function highlightCode() {
           const fakeTextarea = document.getElementById('fakeTextarea');
           const codeContent = fakeTextarea.innerText;
           fakeTextarea.innerHTML = `&lt;code&gt;${hljs.highlightAuto(codeContent).value}&lt;/code&gt;`;
         }
         
         function escapeCode() {
           const fakeTextarea = document.getElementById("fakeTextarea");
           const escapedCode = htmlEscape(fakeTextarea.innerText);
           fakeTextarea.innerText = escapedCode;
           copyToClipboard(escapedCode);
           highlightCode(); // Re-highlight the escaped code
         }
         
         function formatCode() {
           const fakeTextarea = document.getElementById("fakeTextarea");
           const formattedCode = formatSourceCode(fakeTextarea.innerText);
           fakeTextarea.innerText = formattedCode;
           fakeTextarea.style.overflowX = 'auto'; // Enable horizontal scrollbar after formatting
           copyToClipboard(formattedCode);
           highlightCode(); // Re-highlight the formatted code
         }
         
         function htmlEscape(text) {
           return text.replace(/[&lt;&gt;&amp;]/g, function (tag) {
             const replacements = {
               '&lt;': '&amp;lt;',
               '&gt;': '&amp;gt;',
               '&amp;': '&amp;amp;'
             };
             return replacements[tag] || tag;
           });
         }
         
         function copyToClipboard(text) {
           const el = document.createElement("textarea");
           el.value = text;
           document.body.appendChild(el);
           el.select();
           document.execCommand("copy");
           document.body.removeChild(el);
         }
         
         function formatSourceCode(code) {
           const tabSize = 2;
           const lines = code.split('\n');
           let formattedCode = '';
           let indent = 0;
         
           lines.forEach((line, index) =&gt; {
             line = line.trim();
         
             if (line.endsWith('}')) {
               indent -= tabSize;
             }
         
             formattedCode += ' '.repeat(indent) + line + '\n';
         
             if (line.endsWith('{')) {
               indent += tabSize;
             }
           });
         
           return formattedCode.trim();
         }
         
         function resetInput() {
           const fakeTextarea = document.getElementById("fakeTextarea");
           fakeTextarea.innerText = '';
           fakeTextarea.style.overflowX = 'auto'; // Reset horizontal scrollbar to auto
         }
         
         let cursorPosition = 0;
         
         document.getElementById('fakeTextarea').addEventListener('keydown', function(e) {
           cursorPosition = window.getSelection().getRangeAt(0).startOffset;
         });
         
         document.getElementById('fakeTextarea').addEventListener('blur', function(e) {
           const selection = window.getSelection();
           const range = document.createRange();
           range.setStart(this.firstChild, cursorPosition);
           range.collapse(true);
           selection.removeAllRanges();
           selection.addRange(range);
         });
         
         // Call highlightCode initially to highlight any initial content in the "textarea"
         highlightCode();
      &lt;/script&gt;
   &lt;/body&gt;
&lt;/html&gt;
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
 
   
                      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">    Only hilight.js with copy  </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">
&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
   &lt;head&gt;

      &lt;meta charset="UTF-8"&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
      &lt;meta http-equiv="X-UA-Compatible" content="ie=edge"&gt;
      &lt;title&gt;Document&lt;/title&gt;
            &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/highlight.min.js"&gt;&lt;/script&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/languages/javascript.min.js"&gt;&lt;/script&gt;
      &lt;script&gt;
         hljs.highlightAll();
      &lt;/script&gt;
      &lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&gt;
      
   &lt;/head&gt;
   &lt;body&gt;
      &lt;!--      Start       --&gt;
      &lt;pre style="width: 90vw; margin: auto; position: relative; display: flex; flex-wrap: nowrap; margin-bottom: 20px; border: 2px solid gray; background: #f5f5f5; overflow-x: auto; border-radius: 10px; background: #000; max-height: 40vh;color: white;"&gt;&lt;code style="background: black;" class="language-html"&gt;
      &amp;lt;!--      Start       --&amp;gt;
               
               
               

        &amp;lt;div class="response"&amp;gt;
           &amp;lt;pre&amp;gt;&amp;lt;code style="background: black;" class="language-html"&amp;gt;
 
   
            &amp;lt;/code&amp;gt;&amp;lt;/pre&amp;gt;
           &amp;lt;button class="copy-button"&amp;gt;Copy.    &amp;lt;/button&amp;gt;
        &amp;lt;/div&amp;gt;

      
      &amp;lt;!--      End       --&amp;gt;

 
   
 
   
            &lt;/code&gt;&lt;button class="copy-button" style="position: absolute; top: 10px; right: 10px; height: 25px; padding: 4px 8px; border: none; border-radius: 4px; background-color: #007bff; color: #fff; cursor: pointer;" onclick="copyResponseText(this)"&gt;Copy&lt;/button&gt;

      &lt;/pre&gt;
      &lt;!--      End       --&gt;

       
      &lt;script&gt;
         function copyResponseText() {
           const responseTextElement = this.previousElementSibling;
           const textToCopy = responseTextElement.innerText;
         
          
           const tempTextArea = document.createElement('textarea');
           tempTextArea.value = textToCopy;
           document.body.appendChild(tempTextArea);
         
         
           tempTextArea.select();
           document.execCommand('copy');
         
           
           document.body.removeChild(tempTextArea);
         
         
           this.innerText = 'Copied!';
           setTimeout(() =&gt; {
             this.innerText = 'Copy';
           }, 2000);
         }
         
         
         const copyButtons = document.querySelectorAll('.copy-button');
         copyButtons.forEach((button) =&gt; {
           button.addEventListener('click', copyResponseText);
         });
      &lt;/script&gt;
   &lt;/body&gt;
&lt;/html&gt; 
   
                

                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
 
   
                      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">  Code ka code    </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
   &lt;head&gt;
      &lt;meta charset="UTF-8" /&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1.0" /&gt;
      &lt;meta http-equiv="X-UA-Compatible" content="ie=edge" /&gt;
      &lt;title&gt;Document&lt;/title&gt;
      &lt;!-- highlight.js library --&gt;
      &lt;!--   &lt;link rel="stylesheet" href="://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/windows-10.min.css" integrity="sha512-MHq77y3maCJBc1Qp8YgCGVZ/f+st6FasSlt5iVAEkzDwfnKshFTrfFqXhWtNCFqS1zcGgl7Cur2uiIPcw4hHYA==" crossorigin="anonymous" referrerpolicy="no-referrer" /&gt; --&gt;
      &lt;!-- &lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/a11y-dark.min.css" integrity="sha512-Vj6gPCk8EZlqnoveEyuGyYaWZ1+jyjMPg8g4shwyyNlRQl6d3L9At02ZHQr5K6s5duZl/+YKMnM3/8pDhoUphg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&gt; --&gt;
      &lt;link
         rel="stylesheet"
         href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css"
         integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg=="
         crossorigin="anonymous"
         referrerpolicy="no-referrer"
         /&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/highlight.min.js"&gt;&lt;/script&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/languages/javascript.min.js"&gt;&lt;/script&gt;
      &lt;script&gt;
         hljs.highlightAll();
      &lt;/script&gt;
      &lt;style&gt;
         .g {
         border: 1px dashed darkturquoise;
         display: block;
         }
         a {
         color: red;
         }
         h2 {
         margin-top: 150px;
         text-align: center;
         }
         p {
         width: 90vw;
         margin: auto;
         }
         h2 {
         text-align: center;
         }
         /* Styles for the response container */
         .response {
         margin: auto;
         box-shadow: 0 0 10px rgba(0, 0, 0, 0.2), 0 0 10px rgba(0, 0, 0, 0.4), 0 0 10px rgba(0, 0, 0, 0.6);
         /* box-shadow: 0 0 10px rgba(0, 0, 0, 0.5), 0 0 20px rgba(0, 0, 0, 0.5), 0 0 30px rgba(0, 0, 0, 0.5); */
         position: relative;
         display: flex;
         flex-wrap: nowrap; /* Prevent wrapping of boxes when scrolling horizontally */
         margin-bottom: 20px;
         background: black;
         overflow-x: auto; /* Enable horizontal scrolling */
         border-radius: 10px;
         max-height: 40vh;
         color: white;
         padding-left: 14px;
         }
         .res {
         width: 90vw;
         margin: auto;
         position: relative;
         display: flex;
         flex-wrap: nowrap; /* Prevent wrapping of boxes when scrolling horizontally */
         margin-bottom: 20px;
         background: black;
         overflow-x: auto; /* Enable horizontal scrolling */
         border-radius: 10px;
         line-height:30px;
         color: white;
         padding-left: 14px;
         }
         /* Styles for the copy button */
         .copy-button {
         position: sticky;
         top: 10px;
         right: 10px;
         height: 25px;
         padding: 4px 8px;
         border: none;
         border-radius: 4px;
         background-color: #007bff;
         color: #fff;
         cursor: pointer;
         }
         .tr {
         position: absolute;
         top: 10px;
         left: 10px;
         height: 25px;
         border: 1px double burlywood;
         border-radius: 4px;
         background-color: #000000;
         color: #fff;
         }
      &lt;/style&gt;
   &lt;/head&gt;
   &lt;body&gt;
      &lt;br /&gt;
      &lt;br /&gt;
      &lt;br /&gt;
      &lt;br /&gt;
      &lt;br /&gt;
      &lt;br /&gt;
      &lt;br /&gt;
      &lt;div class="response"&gt;
         &lt;pre&gt;
        
  
 box-shadow: 0 0 10px rgba(0, 0, 0, 0.2), 0 0 10px rgba(0, 0, 0, 0.4), 0 0 10px rgba(0, 0, 0, 0.6);

&lt;/pre
            &gt;
         &lt;button class="copy-button"&gt;Copy&lt;/button&gt;
      &lt;/div&gt;
      &lt;h2&gt;Aisa 1 box banana hai to&lt;/h2&gt;
      &lt;div class="response"&gt;
         &lt;pre&gt;&lt;code style="background: black;" class="language-html"&gt;
&amp;lt;!--.........box html start..........--&amp;gt;
&amp;lt;div style=&amp;quot;width: 90vw; margin: auto; position: relative; display: flex; flex-wrap: nowrap; margin-bottom: 20px; border: 2px solid gray; background: #f5f5f5; overflow-x: auto; border-radius: 10px; background: #000; max-height: 40vh;color: white;&amp;quot;&amp;gt;
  &amp;lt;pre&amp;gt;
&amp;amp;lt;script&amp;amp;gt;
// Your JavaScript code goes here
 &amp;amp;lt;/script&amp;amp;gt;
 &amp;lt;/pre&amp;gt;
  &amp;lt;/span&amp;gt;
  &amp;lt;button class=&amp;quot;copy-button&amp;quot; style=&amp;quot;position: sticky; top: 10px; right: 10px; height: 25px; padding: 4px 8px; border: none; border-radius: 4px; background-color: #007bff; color: #fff; cursor: pointer;&amp;quot; onclick=&amp;quot;copyResponseText(this)&amp;quot;&amp;gt;Copy&amp;lt;/button&amp;gt;
&amp;lt;/div&amp;gt;
&amp;lt;!--.........Box html End...........--&amp;gt;
&amp;lt;!--............box javascript start........--&amp;gt;
&amp;lt;script&amp;gt;
  function copyResponseText(button) {
    const responseTextElement = button.previousElementSibling;
    const textToCopy = responseTextElement.innerText;
  
    const tempTextArea = document.createElement('textarea');
    tempTextArea.value = textToCopy;
    document.body.appendChild(tempTextArea);
  
    tempTextArea.select();
    document.execCommand('copy');
  
    document.body.removeChild(tempTextArea);
  
    button.innerText = 'Copied!';
    setTimeout(() =&amp;gt; {
      button.innerText = 'Copy';
    }, 2000);
  }
&amp;lt;/script&amp;gt;
&amp;lt;!--..........box javascript end........--&amp;gt;
&lt;/code&gt;&lt;/pre&gt;
         &lt;button class="copy-button"&gt;Copy.&lt;/button&gt;
      &lt;/div&gt;
      &lt;h2&gt;Box ke andr code likhna ho to&lt;/h2&gt;
      &lt;p&gt;
         Agr directly code paste kroge to o show nhi hoga .Code ko phle escape krna
         pdega uske bad paste krna hoga {
         &lt;a href="https://websemantics.uk/tools/escaping-html/"
            &gt;Is website se escape kr sakte&lt;/a
            &gt;} is website se code automatically copy ho jata.........Ab copy code ko
         pre tag ke andr paste
      &lt;/p&gt;
      &lt;h2&gt;Agr 1 se jda box chahiye to&lt;/h2&gt;
      &lt;div class="response"&gt;
         &lt;pre&gt;&lt;code style="background: black;" class="language-javascript"&gt;
     &amp;lt;div class=&amp;quot;response&amp;quot;&amp;gt;
 &amp;lt;pre&amp;gt;
&amp;lt;code style=&amp;quot;background: black;&amp;quot; class=&amp;quot;language-javascript&amp;quot;&amp;gt;
  Box html
&amp;lt;/code&amp;gt;
 &amp;lt;/pre&amp;gt;
  &amp;lt;button class=&amp;quot;copy-button&amp;quot;&amp;gt;Copy.    &amp;lt;/button&amp;gt;
&amp;lt;/div&amp;gt;
 &lt;/code&gt;&lt;/pre&gt;
         &lt;button class="copy-button"&gt;Copy.&lt;/button&gt;
         &lt;button class="tr"&gt;Html&lt;/button&gt;
      &lt;/div&gt;
      &lt;div class="response"&gt;
         &lt;pre&gt;
&lt;code style="background: black;" class="language-html"&gt;
&amp;lt;style&amp;gt;
  .response {
    width: 90vw;
    margin: auto;
    position: relative;
    display: flex;
    flex-wrap: nowrap; /* Prevent wrapping of boxes when scrolling horizontally */
    margin-bottom: 20px;
    background: black;
    overflow-x: auto; /* Enable horizontal scrolling */
    border-radius: 10px;
    max-height: 40vh;
    color: white;
    padding-left: 14px;
  }

  /* Styles for the copy button */
  .copy-button {
    position: sticky;
    top: 10px;
    right: 10px;
    height: 25px;
    padding: 4px 8px;
    border: none;
    border-radius: 4px;
    background-color: #007bff;
    color: #fff;
    cursor: pointer;
  }
&amp;lt;/style&amp;gt;

&lt;/code&gt;
 &lt;/pre&gt;
         &lt;button class="copy-button"&gt;Copy.&lt;/button&gt;
         &lt;button class="tr"&gt;Css&lt;/button&gt;
      &lt;/div&gt;
      &lt;div class="response"&gt;
         &lt;pre&gt;
&lt;code style="background: black;" class="language-javascript"&gt;
        &amp;lt;script&amp;gt;
    
    function copyResponseText() {
      const responseTextElement = this.previousElementSibling;
      const textToCopy = responseTextElement.innerText;

     
      const tempTextArea = document.createElement(&amp;apos;textarea&amp;apos;);
      tempTextArea.value = textToCopy;
      document.body.appendChild(tempTextArea);

    
      tempTextArea.select();
      document.execCommand(&amp;apos;copy&amp;apos;);

      
      document.body.removeChild(tempTextArea);

   
      this.innerText = &amp;apos;Copied!&amp;apos;;
      setTimeout(() =&amp;gt; {
        this.innerText = &amp;apos;Copy&amp;apos;;
      }, 2000);
    }


    const copyButtons = document.querySelectorAll(&amp;apos;.copy-button&amp;apos;);
    copyButtons.forEach((button) =&amp;gt; {
      button.addEventListener(&amp;apos;click&amp;apos;, copyResponseText);
    });
  &amp;lt;/script&amp;gt;

&lt;/code&gt;
 &lt;/pre&gt;
         &lt;button class="copy-button"&gt;Copy.&lt;/button&gt;
         &lt;button class="tr"&gt;Javascript&lt;/button&gt;
      &lt;/div&gt;
      &lt;h2&gt;Html Css aur Javascript ko kaise ak code me jode&lt;/h2&gt;
      &lt;p&gt;
         Html code likhne ke bad body tag ke upr style tag me Css aur script tag me
         javascript add kr skte hai
      &lt;/p&gt;
      &lt;pre&gt;&lt;code style="background: black;" class="language-javascript"&gt;
  &amp;lt;!DOCTYPE html&amp;gt;
&amp;lt;html&amp;gt;
&amp;lt;head&amp;gt;
  
&lt;span class="g"&gt;  &amp;lt;style&amp;gt;
    
    css code yaha
    
  &amp;lt;/style&amp;gt;&lt;/span&gt;
  
&lt;span class="g"&gt; &amp;lt;script&amp;gt;
    
    javascript code yaha 
    
  &amp;lt;/script&amp;gt;
&lt;/span&gt;
&amp;lt;/head&amp;gt;

&lt;span class="g"&gt;&amp;lt;body&amp;gt;
  html code yaha 
&amp;lt;/body&amp;gt;&lt;/span&gt;

&amp;lt;/html&amp;gt;
&lt;/code&gt;&lt;/pre&gt;
      &lt;h2&gt;Agar colourful code chahiye&lt;/h2&gt;
      &lt;div class="response"&gt;
         &lt;pre&gt;
&lt;code style="background: black;" class="language-html"&gt;
      &amp;lt;!--      Start       --&amp;gt;
               
                            
        &amp;lt;div class="response"&amp;gt;
           &amp;lt;pre&amp;gt;&amp;lt;code style="background: black;" class="language-html"&amp;gt;
 
            &amp;lt;/code&amp;gt;&amp;lt;/pre&amp;gt;
           &amp;lt;button class="copy-button"&amp;gt;Copy.    &amp;lt;/button&amp;gt;
        &amp;lt;/div&amp;gt;

      
      &amp;lt;!--      End       --&amp;gt;

 
   


&lt;/code&gt;
 &lt;/pre&gt;
         &lt;button class="copy-button"&gt;Copy.&lt;/button&gt;
      &lt;/div&gt;
      &lt;div class="response"&gt;
         &lt;pre&gt;
&lt;code style="background: black;" class="language-javascript"&gt;
  &amp;lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/highlight.min.js"&amp;gt;&amp;lt;/script&amp;gt;
  &amp;lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/languages/javascript.min.js"&amp;gt;&amp;lt;/script&amp;gt;


  &amp;lt;script&amp;gt;
    hljs.highlightAll();
  &amp;lt;/script&amp;gt;
  
  
  &amp;lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&amp;gt;

 &lt;/code&gt;&lt;/pre&gt;
         &lt;button class="copy-button"&gt;Copy.&lt;/button&gt;
      &lt;/div&gt;
      &lt;p&gt;
         Itna krne ke bad ab theme choose krna hai ki kaisa chaiye {&lt;a
            href="https://highlightjs.org/static/demo/"
            &gt;Yaha se theme select kr sakte&lt;/a
            &gt;}
      &lt;/p&gt;
      &lt;br /&gt;
      &lt;p&gt;
         Ab us theme ka naam
         &lt;a href="https://cdnjs.com/libraries/highlight.js"
            &gt;is website {select styling in asset type}&lt;/a
            &gt;me search krke copy wale me second wale pr click krke code copy
      &lt;/p&gt;
      &lt;br /&gt;
      &lt;p&gt;Us code ko apne website me head tag ke upr paste}&lt;/p&gt;
      &lt;br /&gt;
      &lt;div class="response"&gt;
         &lt;pre&gt;&lt;code style="background: black;" class="language-javascript"&gt;
&amp;lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&amp;gt;
&lt;/code&gt;&lt;/pre&gt;
         &lt;button class="copy-button"&gt;Copy.&lt;/button&gt;
      &lt;/div&gt;
      &lt;br /&gt;
      &lt;br /&gt;
      &lt;script&gt;
         // Function to copy the text inside the response-text element when the copy button is clicked
         function copyResponseText() {
           const responseTextElement = this.previousElementSibling;
           const textToCopy = responseTextElement.innerText;
         
           // Create a temporary textarea element to hold the text to be copied
           const tempTextArea = document.createElement('textarea');
           tempTextArea.value = textToCopy;
           document.body.appendChild(tempTextArea);
         
           // Select and copy the text
           tempTextArea.select();
           document.execCommand('copy');
         
           // Remove the temporary textarea
           document.body.removeChild(tempTextArea);
         
           // Provide some visual feedback to the user
           this.innerText = 'Copied!';
           setTimeout(() =&gt; {
             this.innerText = 'Copy';
           }, 2000);
         }
         
         // Attach the copyResponseText function to all copy buttons
         const copyButtons = document.querySelectorAll('.copy-button');
         copyButtons.forEach((button) =&gt; {
           button.addEventListener('click', copyResponseText);
         });
      &lt;/script&gt;
   &lt;/body&gt;
&lt;/html&gt;
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
 
   
                      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   PW link changer   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">
&lt;!DOCTYPE html&gt;
&lt;html&gt;

&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
  &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
  &lt;meta http-equiv="X-UA-Compatible" content="ie=edge"&gt;
    &lt;title&gt;Link Converter&lt;/title&gt;
    &lt;style&gt;
       
        body {
            font-family: Arial, sans-serif;
            /* text-align: center; */
            margin: 0 20px; /* Equal margin from left and right */
        }

        h1 {
            margin-top: 20px;
        }

        label, input[type="text"], button, #outputLink, p {
            margin: 10px 0;
        }

        input[type="text"] {
            width: 90%;
            padding: 10px;
            font-size: 14px;
        }

        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }

        #outputLink a {
            color: #007bff;
            text-decoration: none;
        }

        /* Styles for the Link Converter */
        .output-link {
            margin-bottom: 10px; /* Add space between link and quality */
        }

        .output-link a {
            color: #007BFF; /* Blue color for links */
            text-decoration: none;
            cursor: pointer; /* Change cursor to pointer */
        }

        .output-quality {
            font-weight: bold;
            color: black; /* Black color for quality text */
            display: block; /* Display quality text in a new line */
        }
    &lt;/style&gt;
&lt;/head&gt;

&lt;body&gt;
    &lt;h1&gt;Link Converter&lt;/h1&gt;
    &lt;input type="text" id="linkInput" placeholder="......"&gt;
    &lt;button id="convertButton" onclick="convertLink()"&gt;Convert&lt;/button&gt;
    &lt;div id="outputLink"&gt;&lt;/div&gt;

    &lt;script&gt;
        function convertLink() {
            const inputLink = document.getElementById('linkInput').value.trim();
            const output = document.getElementById('outputLink');
            output.innerHTML = '';

            if (inputLink.includes('cloudfront')) {
                const videoIdMatch = inputLink.match(/\/([^/]+)\/dash\//);

                if (videoIdMatch &amp;&amp; videoIdMatch.length &gt;= 2) {
                    const videoId = videoIdMatch[1];
                    const qualities = ['144', '240', '360', '480', '720'];

                    qualities.forEach(quality =&gt; {
                        const url = `https://d26g5bnklkwsh4.cloudfront.net/${videoId}/hls/${quality}/main.m3u8`;
                        const linkElement = document.createElement('p');
                        linkElement.classList.add('output-link');

                        // Create the quality and link elements
                        const qualityElement = document.createElement('h3');
                        qualityElement.classList.add('output-quality');
                        qualityElement.innerText = `${quality} Quality`;

                        const link = document.createElement('a');
                        link.href = "#"; // Set href as "#" to prevent link opening
                        link.innerText = url;

                        // Attach a click event listener to copy the URL to clipboard
                        link.addEventListener('click', function() {
                            copyToClipboard(url);
                        });

                        // Append quality and link to the output element
                        linkElement.appendChild(qualityElement);
                        linkElement.appendChild(link);
                        output.appendChild(linkElement);
                    });
                } else {
                    const invalidLinkText = document.createElement('p');
                    invalidLinkText.classList.add('output-link');
                    invalidLinkText.innerText = 'Invalid input link. Please provide a valid link.';
                    output.appendChild(invalidLinkText);
                }
            } else {
                const noCloudfrontText = document.createElement('p');
                noCloudfrontText.classList.add('output-link');
                noCloudfrontText.innerText = 'Input link does not contain "cloudfront".';
                output.appendChild(noCloudfrontText);
            }
        }

        function copyToClipboard(text) {
            const el = document.createElement('textarea');
            el.value = text;
            document.body.appendChild(el);
            el.select();
            document.execCommand('copy');
            document.body.removeChild(el);
        }
    &lt;/script&gt;
&lt;/body&gt;

&lt;/html&gt;

 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
 
   
                      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   Fix background img   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-css">  body {
      background-image: url('/mn-ipacky21-316-kglking-original-imagfu86wushddyn.jpeg'); /* Replace with your image URL */
      background-size: cover;
      background-attachment: fixed; /* This makes the background image fixed */
    }
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
 
   
                      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">    Another rectangular accordion  </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">&lt;!DOCTYPE html&gt;
&lt;html&gt;
   &lt;head&gt;
      &lt;meta charset="UTF-8"&gt;
      &lt;meta name="viewport" content="width=device-width, initial-scale=1"&gt;
      &lt;title&gt;&lt;/title&gt;
      &lt;link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/base16/humanoid-dark.min.css" integrity="sha512-VpzmzXvIXjYfKE4xjvTjF41gt15bbXf3u0CDWXDm105TA7yphqLSVqAc+gnpJswiS068uRYqiXCC4MvCycjQhg==" crossorigin="anonymous" referrerpolicy="no-referrer" /&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/highlight.min.js"&gt;&lt;/script&gt;
      &lt;script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.7.2/languages/javascript.min.js"&gt;&lt;/script&gt;
      &lt;script&gt;
         hljs.highlightAll();
      &lt;/script&gt;
      &lt;style&gt;
         .response {
         width: 85vw;
         margin-top: 100px;
         margin: auto;
         position: relative;
         display: flex;
         flex-wrap: nowrap; /* Prevent wrapping of boxes when scrolling horizontally */
         margin-bottom: 20px;
         background: black;
         overflow-x: auto; /* Enable horizontal scrolling */
         border-radius: 10px;
         max-height: 40vh;
         color: white;
         padding-left: 14px;
         }
         /* Styles for the copy button */
         .copy-button {
         position: sticky;
         top: 10px;
         right: 10px;
         height: 25px;
         padding: 4px 8px;
         border: none;
         border-radius: 4px;
         background-color: #007bff;
         color: #fff;
         cursor: pointer;
         }
      &lt;/style&gt;
      &lt;style&gt;
         @import url(https://fonts.googleapis.com/css?family=Lato:400,700);
         * {
         -moz-box-sizing: border-box;
         -webkit-box-sizing: border-box;
         box-sizing: border-box;
         }
         *{
         /* background: #000; */!important
         }
         body {
         font-family: 'Lato';
         }
         h1 {
         font-size: 2em;
         padding: 2em;
         text-align: center;
         }
         .accordion dl {
         }
         .accordion dt @import url(https://fonts.googleapis.com/css?family=Lato:400,700);
         * {
         -moz-box-sizing: border-box;
         -webkit-box-sizing: border-box;
         box-sizing: border-box;
         }
         body {
         font-family: 'Lato';
         }
         h1 {
         font-size: 2em;
         padding: 2em;
         text-align: center;
         }
         .accordion dl {
         }
         .accordion dt &gt; a {
         text-align: center;
         font-weight: 700;
         padding: 2em;
         display: block;
         text-decoration: none;
         color: #fff;
         -webkit-transition: background-color 0.5s ease-in-out;
         }
         .accordion dd {
         color:#fafafa;
         font-size: 1em;
         line-height: 1.5em;
         }
         .accordion dd &gt; p {
         padding: 1em 2em 1em 2em;
         }
         .accordion {
         position: relative;
         background-color: #16a085;
         }
         .container {
         max-width: 960px;
         margin: 0 auto;
         padding: 2em 0 2em 0;
         }
         .accordionTitle:before {
         content: "+";
         font-size: 1.5em;
         line-height: 0.5em;
         float: left;
         -moz-transition: -moz-transform 0.4s ease-in-out;
         -o-transition: -o-transform 0.4s ease-in-out;
         -webkit-transition: -webkit-transform 0.4s ease-in-out;
         transition: transform 0.4s ease-in-out;
         }&gt; a {
         text-align: center;
         font-weight: 700;
         padding: 2em;
         display: block;
         text-decoration: none;
         color: #fff;
         -webkit-transition: background-color 0.5s ease-in-out;
         }
         .gitb{
         text-align: center;
         font-weight: 700;
         padding: 2em;
         display: block;
         text-decoration: none;
         color: #fff;
         width: 90vw;
         margin: auto;
         background-color: #22313F;
         border-bottom: 1px solid #2c3e50;
         }
         .accordionTitle {
         width: 90vw;
         margin: auto;
         background-color: #22313F;
         border-bottom: 1px solid #2c3e50;
         }
         .accordion dd {
         background-color: white;
         color:#fafafa;
         font-size: 1em;
         margin-left: 0; 
         margin: 0px 20px;
         /* jisme sara text hai o black colour */
         line-height: 1.5em;
         }
         .accordion dd &gt; p {
         padding: 1em 2em 1em 2em;
         }
         .accordion {
         position: relative;
         background-color: white; /* gap between those */
         }
         .git{
         display: block;
         width: 90%;
         margin: auto;
         border-radius: 40px;
         padding-top: 15px;
         text-decoration: none;
         height: 60px;
         text-align: center;
         margin-top: 30px;
         border: 1px solid black;
         }
         .container {
         max-width: 960px;
         margin: 0 auto;
         padding: 2em 0 2em 0;
         }
         .accordionTitle {
         background-color: #22313F;
         border-bottom: 1px solid #2c3e50;
         }
         .accordionTitle:before {
         content: "+";
         font-size: 1.5em;
         line-height: 0.5em;
         float: left;
         -moz-transition: -moz-transform 0.4s ease-in-out;
         -o-transition: -o-transform 0.4s ease-in-out;
         -webkit-transition: -webkit-transform 0.4s ease-in-out;
         transition: transform 0.4s ease-in-out;
         }
         .accordionTitle:hover {
         background-color: #2c3e50;
         }
         .accordionTitleActive {
         background-color:#34495e;
         }
         .accordionTitleActive:before {
         -webkit-transform: rotate(-225deg);
         -moz-transform: rotate(-225deg);
         transform: rotate(-225deg);
         }
         .accordionItem {
         height: auto;
         overflow: hidden;
         }
         @media all {
         .accordionItem {
         max-height: 70em;
         -moz-transition: max-height 2s;
         -o-transition: max-height 2s;
         -webkit-transition: max-height 1s;
         transition: max-height 1s;
         }
         }
         @media screen and (min-width: 48em) {
         .accordionItem {
         max-height: 15em;
         -moz-transition: max-height 0.7s;
         -o-transition: max-height 0.7s;
         -webkit-transition: max-height 0.7s;
         transition: max-height 0.7s;
         }
         }
         .accordionItemCollapsed {
         max-height: 0;
         }
         .animateIn {
         -webkit-animation-name: accordionIn;
         -webkit-animation-duration: 0.65s;
         -webkit-animation-iteration-count: 1;
         -webkit-animation-direction: normal;
         -webkit-animation-timing-function: ease-in-out;
         -webkit-animation-fill-mode: both;
         -webkit-animation-delay: 0s;
         -moz-animation-name: normal;
         -moz-animation-duration: 0.65s;
         -moz-animation-iteration-count: 1;
         -moz-animation-direction: alternate;
         -moz-animation-timing-function: ease-in-out;
         -moz-animation-fill-mode: both;
         -moz-animation-delay: 0s;
         animation-name: accordionIn;
         animation-duration: 1s;
         animation-iteration-count: 1;
         animation-direction: normal;
         animation-timing-function: ease-in-out;
         animation-fill-mode: both;
         animation-delay: 0s;
         }
         .animateOut {
         -webkit-animation-name: accordionOut;
         -webkit-animation-duration: 0.75s;
         -webkit-animation-iteration-count: 1;
         -webkit-animation-direction: alternate;
         -webkit-animation-timing-function: ease-in-out;
         -webkit-animation-fill-mode: both;
         -webkit-animation-delay: 0s;
         -moz-animation-name: accordionOut;
         -moz-animation-duration: 0.75s;
         -moz-animation-iteration-count: 1;
         -moz-animation-direction: alternate;
         -moz-animation-timing-function: ease-in-out;
         -moz-animation-fill-mode: both;
         -moz-animation-delay: 0s;
         animation-name: accordionOut;
         animation-duration: 0.75s;
         animation-iteration-count: 1;
         animation-direction: alternate;
         animation-timing-function: ease-in-out;
         animation-fill-mode: both;
         animation-delay: 0s;
         }
         @-webkit-keyframes accordionIn {
         0% {
         opacity: 0;
         -webkit-transform: scale(0.8);
         }
         100% {
         opacity: 1;
         -webkit-transform: scale(1);
         }
         }
         @-moz-keyframes accordionIn {
         0% {
         opacity: 0;
         -moz-transform: scale(0.8);
         }
         100% {
         opacity: 1;
         -moz-transform: scale(1);
         }
         }
         @keyframes accordionIn {
         0% {
         opacity: 0;
         transform: scale(0.8);
         }
         100% {
         opacity: 1;
         transform: scale(1);
         }
         }
         @-webkit-keyframes accordionOut {
         0% {
         opacity: 1;
         -webkit-transform: scale(1);
         }
         100% {
         opacity: 0;
         -webkit-transform: scale(0.8);
         }
         }
         @-moz-keyframes accordionOut {
         0% {
         opacity: 1;
         -moz-transform: scale(1);
         }
         100% {
         opacity: 0;
         -moz-transform: scale(0.8);
         }
         }
         @keyframes accordionOut {
         0% {
         opacity: 1;
         transform: scale(1);
         }
         100% {
         opacity: 0;
         transform: scale(0.8);
         }
         }
      &lt;/style&gt;
   &lt;/head&gt;
   &lt;body&gt;
      &lt;div class="container"&gt;
         &lt;h1&gt;Simple Flat UI CSS Accordion&lt;/h1&gt;
         &lt;div class="accordion"&gt;
            &lt;br&gt;
            &lt;dt&gt;&lt;a href="#" class="accordionTitle"&gt;Aise box ke liye ye code &lt;/a&gt;&lt;/dt&gt;
            &lt;dd class="accordionItem accordionItemCollapsed"&gt;
               &lt;br&gt;
               &lt;div class="response"&gt;
                  &lt;pre&gt;&lt;code style="background: black;" class="language-html"&gt;      &amp;lt;!--      Start       --&amp;gt;
               
               
               
             &amp;lt;br&amp;gt;
        &amp;lt;dt&amp;gt;&amp;lt;a href="#" class="accordionTitle"&amp;gt;Aise box ke liye ye code &amp;lt;/a&amp;gt;&amp;lt;/dt&amp;gt;

        &amp;lt;dd class="accordionItem accordionItemCollapsed"&amp;gt;
           &amp;lt;br&amp;gt;
           &amp;lt;div class="response"&amp;gt;
              &amp;lt;pre&amp;gt;&amp;lt;code style="background: black;" class="language-html"&amp;gt;
  
              &amp;lt;/code&amp;gt;&amp;lt;/pre&amp;gt;
              &amp;lt;button class="copy-button"&amp;gt;Copy.    &amp;lt;/button&amp;gt;
           &amp;lt;/div&amp;gt;
        &amp;lt;/dd&amp;gt;
      
      
      &amp;lt;!--      End       --&amp;gt;

 
                  &lt;/code&gt;&lt;/pre&gt;
                  &lt;button class="copy-button"&gt;Copy.    &lt;/button&gt;
               &lt;/div&gt;
               
               
               
                              
                              &lt;h5 style="color: black;"&gt;Link add&lt;/h5&gt;
               &lt;div class="response"&gt;
                  &lt;pre&gt;&lt;code style="background: black;" class="language-html"&gt;
&amp;lt;dt&amp;gt;&amp;lt;a href="#" class="accordionTitle"&amp;gt;Test Simple Flat UI CSS Accordion 2&amp;lt;/a&amp;gt;&amp;lt;/dt&amp;gt;
&amp;lt;dd class="accordionItem accordionItemCollapsed"&amp;gt;

&amp;lt;a href="" class="git"&amp;gt;link 39&amp;lt;/a&amp;gt;
&amp;lt;a href="" class="git"&amp;gt;link 40&amp;lt;/a&amp;gt;

&amp;lt;/dd&amp;gt;
&amp;lt;br&amp;gt;

                  &lt;/code&gt;&lt;/pre&gt;
                  &lt;button class="copy-button"&gt;Copy.    &lt;/button&gt;
               &lt;/div&gt;
               
            &lt;/dd&gt;
            &lt;br&gt;
            &lt;dt&gt;&lt;a href="#" class="accordionTitle"&gt;Test Simple Flat UI CSS Accordion 2&lt;/a&gt;&lt;/dt&gt;
            &lt;dd class="accordionItem accordionItemCollapsed"&gt;
               &lt;a href="" class="git"&gt;link 39&lt;/a&gt;
               &lt;a href="" class="git"&gt;link 40&lt;/a&gt;
                              &lt;a href="" class="git"&gt;link 39&lt;/a&gt;
                              &lt;a href="" class="git"&gt;link 40&lt;/a&gt;
            &lt;/dd&gt;
            &lt;br&gt;
            &lt;a href="https://example.com/" class="gitb"&gt;Test Simple Flat UI CSS Accordion 3&lt;/a&gt;
            &lt;br&gt;







&lt;!--       ***************************************

          All code above this 

 ************************""""""""""""""" --&gt;


         &lt;/div&gt;
      &lt;/div&gt;
      &lt;div style="height: 50vh;" &gt; &lt;/div&gt;
      &lt;script&gt;
         /*!
          * classie - class helper functions
          * from bonzo https://github.com/ded/bonzo
          *
          * classie.has( elem, 'my-class' ) -&gt; true/false
          * classie.add( elem, 'my-new-class' )
          * classie.remove( elem, 'my-unwanted-class' )
          * classie.toggle( elem, 'my-class' )
          */
         
         /*jshint browser: true, strict: true, undef: true */
         /*global define: false */
         (function(window) {
           'use strict';
         
           function classReg(className) {
             return new RegExp("(^|\\s+)" + className + "(\\s+|$)");
           }
           var hasClass, addClass, removeClass;
         
           if ('classList' in document.documentElement) {
             hasClass = function(elem, c) {
               return elem.classList.contains(c);
             };
             addClass = function(elem, c) {
               elem.classList.add(c);
             };
             removeClass = function(elem, c) {
               elem.classList.remove(c);
             };
           } else {
             hasClass = function(elem, c) {
               return classReg(c).test(elem.className);
             };
             addClass = function(elem, c) {
               if (!hasClass(elem, c)) {
                 elem.className = elem.className + ' ' + c;
               }
             };
             removeClass = function(elem, c) {
               elem.className = elem.className.replace(classReg(c), ' ');
             };
           }
         
           function toggleClass(elem, c) {
             var fn = hasClass(elem, c) ? removeClass : addClass;
             fn(elem, c);
           }
           var classie = {
             hasClass: hasClass,
             addClass: addClass,
             removeClass: removeClass,
             toggleClass: toggleClass,
             has: hasClass,
             add: addClass,
             remove: removeClass,
             toggle: toggleClass
           };
           if (typeof define === 'function' &amp;&amp; define.amd) {
             define(classie);
           } else {
             window.classie = classie;
           }
         })(window);
         var $ = function(selector) {
           return document.querySelector(selector);
         }
         var accordion = $('.accordion');
         accordion.addEventListener("click", function(e) {
           e.stopPropagation();
         
           if (e.target &amp;&amp; e.target.classList.contains("accordionTitle") &amp;&amp; e.target.nodeName == "A") {
             e.preventDefault(); // Prevent the default behavior of the anchor element
         
             var title = e.target;
             var content = e.target.parentNode.nextElementSibling;
             classie.toggle(title, 'accordionTitleActive');
             if (classie.has(content, 'accordionItemCollapsed')) {
               if (classie.has(content, 'animateOut')) {
                 classie.remove(content, 'animateOut');
               }
               classie.add(content, 'animateIn');
             } else {
               classie.remove(content, 'animateIn');
               classie.add(content, 'animateOut');
             }
             classie.toggle(content, 'accordionItemCollapsed');
           }
         });
      &lt;/script&gt;
      &lt;script&gt;
         function copyResponseText() {
           const responseTextElement = this.previousElementSibling;
           const textToCopy = responseTextElement.innerText;
         
          
           const tempTextArea = document.createElement('textarea');
           tempTextArea.value = textToCopy;
           document.body.appendChild(tempTextArea);
         
         
           tempTextArea.select();
           document.execCommand('copy');
         
           
           document.body.removeChild(tempTextArea);
         
         
           this.innerText = 'Copied!';
           setTimeout(() =&gt; {
             this.innerText = 'Copy';
           }, 2000);
         }
         
         
         const copyButtons = document.querySelectorAll('.copy-button');
         copyButtons.forEach((button) =&gt; {
           button.addEventListener('click', copyResponseText);
         });
      &lt;/script&gt;
   &lt;/body&gt;
&lt;/html&gt;
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
       <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   Add this box code   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">      &lt;!--      Start       --&gt;
               
               
               
      &lt;div class="accordion"&gt;
         &lt;button class="accordion-button" onclick="toggleContainer(this)"&gt;      &lt;/button&gt;
         &lt;div class="container closed"&gt;
            &lt;div class="response"&gt;
               &lt;pre&gt;&lt;code style="background: black;" class="language-html"&gt;
 
   
                &lt;/code&gt;&lt;/pre&gt;
               &lt;button class="copy-button"&gt;Copy.    &lt;/button&gt;
            &lt;/div&gt;
            &lt;br&gt;
         &lt;/div&gt;
      &lt;/div&gt;
      
      
      &lt;!--      End       --&gt;

 
   
   
   
   
                
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      <!--      End       -->

 
   
                       
 
   
                
   
                   
   
      <!--      Start       -->
               
               
               
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">   Change selection colour   </button>
         <div class="container closed">
            <div class="response">
               <pre><code style="background: black;" class="language-html">  &lt;style&gt;
  
  /* Pure page ka change krne ke liye */
  
  *::selection{
    
    background: green;
    color: #000;
  }
  
  
  /* Kisi ak element ka change krne ke liye */
  
    div::selection {
      background:black;
      color: white;
    }
    
   /* Kisi ak class ka change krne ke liye  */
    
    .mo::selection{
      background: darkcyan;
      color: gold;
    }
    
    /* Kisi ak Id ka change krne ke liye */
    
    #st::selection{
      background: navajowhite;
      color: #000;
    }
    
  &lt;/style&gt;
 
   
                </code></pre>
               <button class="copy-button">Copy.    </button>
            </div>
            <br>
         </div>
      </div>
      
      
      <!--      End       -->

 
   
   
   
   
                
 
   
                                
 
   
                
   
                
   
                
   
                
   
                                
 
   
                
                      
      
      
      
      
      <!--          start          -->

      
      
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">Simple</button>
         <div class="container closed">
            <p>This is some content inside the first container.</p>
            <pre>
                .
                .
                .
            </pre>
         </div>
      </div>
      
      
      <!--           end           -->








      
      
      <!--          start          -->
      
      
      
      <div class="accordion">
         <button class="accordion-button" onclick="toggleContainer(this)">Link</button>
         <div class="container closed">
            <a href="" class="git">link 1</a>
            <a href="" class="git">link 2</a>
         </div>
      </div>
      
      
      
            <!--           end           -->









      <!-- 
         **********************
         iske phle sb Krna hai 
         
         **********************
         
         
         -->    
      <div style="height: 50vh;" ></div>
      <script>
         function toggleContainer(button) {
             const container = button.nextElementSibling;
             const isOpen = !container.classList.contains('closed');
         
             if (isOpen) {
                 // Container is open, so just close it without scrolling
                 container.style.maxHeight = '0';
                 container.classList.add('closed');
             } else {
                 // Calculate the container's current scroll height before opening
                 const currentScrollHeight = container.scrollHeight;
         
                 // Open the container
                 container.style.maxHeight = currentScrollHeight + 'px';
                 container.classList.remove('closed');
             }
         }
         
         
             
      </script>
      <script>
         function copyResponseText() {
           const responseTextElement = this.previousElementSibling;
           const textToCopy = responseTextElement.innerText;
         
          
           const tempTextArea = document.createElement('textarea');
           tempTextArea.value = textToCopy;
           document.body.appendChild(tempTextArea);
         
         
           tempTextArea.select();
           document.execCommand('copy');
         
           
           document.body.removeChild(tempTextArea);
         
         
           this.innerText = 'Copied!';
           setTimeout(() => {
             this.innerText = 'Copy';
           }, 2000);
         }
         
         
         const copyButtons = document.querySelectorAll('.copy-button');
         copyButtons.forEach((button) => {
           button.addEventListener('click', copyResponseText);
         });
      </script>
   </body>
</html>
 
   
````
