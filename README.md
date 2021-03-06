# Tech Talent South
## Blog Project w/ Spring Boot and Thymeleaf

The in-class slides but these bonus features :
* Add edit button to the results page to be able to immediately edit a post you just created.
* Add JS/jQuery to create a confirm pop-up when trying to delete a post.


# My Notes
I finished both the challenges, here are some notes if you're following along:

* To start off, I changed all (*I hope all at least*) the `<a>` tags outside of `<button>` to go inside them.
    * The dimensions of `<a>` were exceeding `<button>`, and it was just easier to do it this way without spending time looking up CSS.
    * So for clicking on the buttons, if you go to the outermost edge, some of them won't work.
        * Please click in the middle of all the buttons to be safe.

* Also, the app.properties is available (with notes) since it doesn't have any API keys in them.
    * The Bootstrap and jQuery version are the most up-to-date versions.
        * *My VS Code was yelling at me to use them instead of the older versions in the slides.*

* The first part was not that difficult, just copy - paste code that's already in our file and change one word.
    * This is found in result.html. *(TTS-Blog-Project/src/main/resources/templates/blogpost/result.html)*
    * The HTML needed :
        ```html
        <button class="btn btn-primary"><a th:href="@{'/blogposts/{id}'(id=${blogPost.id})}">Edit
            Post</a></button>
        ```
        * In the `th:href`, notice the `blogPost.id` at the end. That's what needed to be changed since the first time we used this, we were doing it inside a ThymeLeaf forEach loop where it was called `blog`.

* The second part I did with JavaScript, but also commented beneath is a version of the same thing but without needing JavaScript, purely HTML.
    * Both of these are in index.html. *(TTS-Blog-Project/src/main/resources/templates/blogpost/index.html)*
    * The JavaScript version
        * The HTML needed :
            ```html
            <button .... onclick="return DeletusMaximus()" .... >
            ```
        * And the JavaScript :
            ```js
            DeletusMaximus = () => {
                let result = confirm('Are you sure you want to delete this Blog Post?')
                if (!result) {
                    return false
                }
            }
            ```
            * *I used Arrow Functions to get more familiar with them.*
    * The HTML in-line version
        * HTML :
            ```html
            <button .... onclick="if (!confirm('Are you sure you want to delete this Blog Entry?')) { return false }" .... >
            ```
            * *I personally like this version better, looks cleaner imo, but the task said JavaScript...*



***If you have any questions, please reach out to me @ aaronshank93@gmail.com.***
