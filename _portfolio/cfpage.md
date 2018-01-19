---
layout: post
title: Creole Forth for JavaScript 
feature-img: "img/sample_feature_img.png"
thumbnail-path: "img/cfe_excel.png"
short-description: The third incarnation of Creole Forth, this time in JavaScript .

---

<strong>Summary</strong>

One of the purported strengths of Forth is the simplicity of its execution model. There is no need for the complex parsing and lookahead of conventional infix languages such as C. For this reason, Forth has been ported to a huge variety of environments. While it traditionally has been used in hardware and embedded systems, it can be used just as easily as a scripting language written on top of another application.  

<strong>Explanation</strong>

The two previous environments Creole Forth has been written for (Delphi/Lazarus and Excel with VBA) are distinguished by their sophisticated IDEs which have complex drag-and-drop functionality and widgets. The underlying languages are
also known for complex typing. In contrast, JavaScript doesn't have much of a concept of type

<strong>Approach</strong> 

I have decided to build Creole Forth in JavaScript as a standalone 'library' component with no dependencies to to other JavaScript frameworks, such as jQuery or Angular. So far, development has been done without the use of a web server.  

<strong>Example usage</strong>

<body>
<table>
    <tr>
    <th>Stack</th><th>Input</th>
    </tr>
    <tr>
        <td><textarea id="DataStack" rows="20" cols="8"></textarea></td>
        <td><textarea id="Input" rows="10" cols="75"></textarea>
            <br /><button class="button" onclick="cfjsSubmit()">Submit</button>
        </td>
    </tr>
</table>

