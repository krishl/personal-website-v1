---
layout: post
title:      "JavaScript Drum Kit Notes"
date:       2018-12-08 11:40:48 -0400
permalink:  javascript_drum_kit_notes
---

# JavaScript Drum Kit Notes and Additional Findings

Key topics: keypress events, playing audio, listening for `transitionend` event, `animationend` event

1. Each `keypress` event has a corresponding `keycode` that is associated with that key
2. Data attributes in JavaScript 
    - `data-*`
    - First brought about in HTML when people started making up their own attributes
    - Used to store custom data (e.g. keys) private to the page or application
    - The attribute name should not contain any uppercase letters, and must be at least one character long after the prefix `data-`
    - Do not store content that should be visible and accessible in data attributes, because assistive technology may not access them. In addition, search crawlers may not index data attributes' values.
3. The `element.addEventListener()` method to attaches an event handler to a specified element.
    - Keydown
        - Fires when the user depresses a key. It repeats while the user keeps the key depressed.
    - Keypress
        - Fires when an actual character is being inserted in, for instance, a text input. It repeats while the user keeps the key depressed.
    - Keyup
        - Fires when the user releases a key, after the default action of that key has been performed.
    - Textinput
        - Occurs when some characters are entered into an element. So if the user presses a character key, but the default is prevented onkeydown or onkeypress, the textinput event does not fire since the sequence does not result in a character being added.
4. The Event interface's `preventDefault()` method tells the user agent that if the event does not get explicitly handled, its default action should not be taken as it normally would be.
5. The Document method `querySelector()` returns the first Element within the document that matches the specified selector, or group of selectors. If no matches are found, null is returned.
    - `element = baseElement.querySelector(selectors);`
6. The Element method `querySelectorAll()` returns a static (not live) NodeList representing a list of the document's elements that match the specified group of selectors.
    - `elementList = parentNode.querySelectorAll(selectors);`
7. The `play()` method starts playing the current audio or video.
    - It returns a Promise which is resolved when playback has been successfully started.
8. Use the `pause()` method to pause the current audio/video.
9. `audio|video.currentTime` sets or returns the current position (in seconds) of the audio/video playback. When setting this property, the playback will jump to the specified position.
10. HTML DOM `classList` Property
    - The `classList` property returns the class name(s) of an element, as a DOMTokenList object.
    - This property is useful to add, remove and toggle CSS classes on an element.
    - The `classList` property is read-only, however, you can modify it by using the add() and remove() methods.
    - `key.classList.add('playing')`
        - Does the same thing as `key.addClass('playing')` in jQuery
        - Adds a class to the target element
    - `remove(class1, class2, ...)`
        - Removes one or more class names from an element
    - `toggle(class, true|false)`
        - Toggles between a class name for an element.
        - The first parameter removes the specified class from an element, and returns false. 
            - If the class does not exist, it is added to the element, and the return value is true.
        - The optional second parameter is a Boolean value that forces the class to be added or removed, regardless of whether or not it already existed.
            - Remove a class: element.classList.toggle("classToRemove", false); 
            - Add a class: element.classList.toggle("classToAdd", true);
11. HTML DOM `addEventListener()` Method
    - `element.addEventListener(event, function, useCapture)`
        - event: Required. A String that specifies the name of the event.
        - function: Required. Specifies the function to run when the event occurs. When the event occurs, an event object is passed to the function as the first parameter.
        - useCapture: Optional. A Boolean value that specifies whether the event should be executed in the capturing or in the bubbling phase. 
            - true: The event handler is executed in the capturing phase
            - false: Default. The event handler is executed in the bubbling phase
12. `this` points to what the method was called against. In this project, `this` points to `key`, since that is what `addEventListener` was called against on line 76.
