## 1. Structure a site using semantic HTML to aid accessibility
- use specific names for elements, e.g. `<h1>` <section> <article>
- ensure headers are in order (`<h1>` `<h2>` `<h3>`) and don't skip any
- include different sections for the page (main, header, footer)
- generic `<div>` or `<span>` only used for styling
![Snip20231009_22](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/3bd170df-b510-49e8-9482-b4ba90a3df60)

## 2. Ensure a web page is readable for screen readers
- Use semantic HTML
- use <a> for links and <button> elements
- Add a fieldset and legend to form radio inputs
![Snip20231009_25](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/96e7d3a5-0c27-4786-91df-25ecdc68b453)

## 3. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably
![Snip20231009_26](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/e037b200-5fae-42e6-abf3-83d0a9d9c91e)

## 4. Use various tools to check that our website meets accessibility criteria
- https://www.a11yproject.com/checklist/
- https://validator.w3.org/nu/
- Lighthouse on Google Chrome:
![Lighthouse](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/24e8a1c1-0da9-4fc9-a73b-124cc297db92)

## 5. Use CSS media queries to ensure our content is always presented effectively on screens of different sizes
![Snip20231009_28](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/5f2f2654-dcab-4281-924a-600dd62fe874)

## 6. Demonstrate a mobile-first approach to building a website
- use responsive mode in developer tools to look at screens in different sizes
- use rem sizing, vh, vw to ensure things are sized correctly
- use media queries
- responsive grids! Change depending on screen size:
![Snip20231009_29](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/d59a3466-84c9-4ec4-b153-cc9a0948f996)

## 7. Use CSS variables to apply repeated colours to HTML elements
![Snip20231009_30](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/577a4e1c-7bf6-45d9-872a-b170b8e6c86c)
![Snip20231009_31](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/670b0cd4-3a30-4a29-bde5-970964d385df)
- do these from the start! You can edit them later.

## 8. Use CSS Flexbox to style children in a single-direction layout (ie a row or a column)
e.g.
![Snip20231009_36](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/6f54e1d9-a41d-42f2-853c-b5d7163a2b04)

## 9. Use CSS Grid to style children in two-direction layout
e.g.
![Snip20231009_33](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/24b08d72-c3f0-4f19-b78a-5e2a462fce49)

## 10. Ensure our Git commit history tells a coherent story
- use clear descriptions in your commits
![Snip20231009_32](https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/df2b792f-11d2-4b4f-904f-1456100fb825)

## 11. Use the appropriate input types in HTML forms for gathering different types of information
Input types:
- text
- password
- number
- range (slider)
- checkbox (can select musltiple)
- radio (can select one)
- dropdown
- datalist (creates text field to type option in- good for large amount of options)
- text area (for more text)

Input attributes:
- name (must be included for data to be submitted)
- value (e.g. for radio/datalist/checkbox)
- min, max (for range)
- step (for number- gives little up/down arrows)
- action(e.g. "/example.html- where user is sent once form is submitted)
- method(HTTP verb- GET POST PUT DELETE

Use <label> for each option in form
