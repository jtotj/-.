# jQuery에서 자주 썼던 것을 Javascript로
> Intro
> jQuery 대신 javascript로 크로스 브라우징은 babel로....

<br>

```javascript

$(body) ==>  document.body
$('html') ==> document.documentElement
$(selector) ==> document.querySelector(selector)
$(ele).parent() ==> ele.parentNode
$(ele).closest('.country') ==> ele.closest('.country')
$input.closest('form') ==> input.form
ele.prev() ==> ele.previousElementSibling
$ele.next() ==> ele.nextElementSibling

//input
$input.val() --> input.value
$input.val("hello") --> input.value = "hello"


//event listener

$ele.on(eventName, handler) --> ele.addEventListener(eventName, handler)
$elem.off(eventName) --> elem.removeEventListener(eventName, handler)

$elem.addClass(c) => elem.classList.add(c)
$elem.removeClass(c) => elem.classList.remove(c)
$elem.toggleClass(c) => elem.classList.toggle(c)
$elem.hasClass(c) => elem.classList.contains(c)
$elem.attr('class') = 'some classes' => elem.className = 'some classes'

//scroll
$el.scrollTop() => el.scrollTop
$el.scrollTop(10) => el.scrollTop = 10

$elem.attr("placeholder") => elem.getAttribute("placeholder")
$elem.attr("placeholder", p) => elem.setAttribute("placeholder", p)


```

