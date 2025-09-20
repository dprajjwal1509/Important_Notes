# Technical Paper

## 1. Types of List in HTML

## 1. Ordered List (`<ol>`)

-   Displays items in a sequence with numbers or letters.\
-   Useful when order matters (e.g., steps in a recipe).

**Example:**

``` html
<ol>
  <li>Step One</li>
  <li>Step Two</li>
</ol>
```

------------------------------------------------------------------------

## 2. Unordered List (`<ul>`)

-   Displays items with bullet points.\
-   Useful when order doesn't matter (e.g., shopping list).

**Example:**

``` html
<ul>
  <li>Apples</li>
  <li>Bananas</li>
</ul>
```

------------------------------------------------------------------------

## 3. Description/Definition List (`<dl>`)

-   Used for defining terms and their descriptions.\
-   Consists of:
    -   `<dt>` → Definition Term\
    -   `<dd>` → Definition Description

**Example:**

``` html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language, used to structure web content.</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets, used for styling web pages.</dd>

  <dt>JavaScript</dt>
  <dd>Programming language that adds interactivity to websites.</dd>
</dl>
```


## 2. List Flattening
List flattening means converting a nested list (multi-level list) into a single-level list.  
It is commonly used in data processing to simplify operations.

Example in Python:  
```python
nested_list = [[1, 2], [3, 4], [5]]
flattened = [x for sublist in nested_list for x in sublist]
# Output: [1, 2, 3, 4, 5]
```

## 3. Cookies in Web Development
Cookies are small text files stored in the browser by websites.  
They help websites remember user preferences, sessions, and login states.

- Used for authentication, personalization, and tracking.  
- Example: When you log in, a cookie keeps you signed in even after refreshing the page.

## 4. Merge Sort
Merge Sort is a **divide-and-conquer algorithm**:
1. Split the list into two halves.  
2. Recursively sort both halves.  
3. Merge them into a single sorted list.

- Efficient for large datasets.  
- Time Complexity: **O(n log n)**  
- Space Complexity: **O(n)**

## 5. Virtual Environment
A **virtual environment** in Python is a self-contained environment that allows you to install packages specific to a project.  
This avoids version conflicts when working on multiple projects.

- Example commands:  
```bash
python -m venv myenv
source myenv/bin/activate   # Linux/Mac
myenv\Scripts\activate    # Windows
```

## 6. Shallow Copy vs Deep Copy
- **Shallow Copy**: Creates a new object but nested objects are still linked.  
- **Deep Copy**: Creates a completely independent object with copies of nested objects.

Example:  
```python
import copy
list1 = [[1,2], [3,4]]
shallow = copy.copy(list1)    # Nested lists are shared
deep = copy.deepcopy(list1)   # Completely new copy
```

## 6.1 Similarity Between Stack and Heap
- Both are memory areas used by programs.  
- **Stack**: Stores local variables and function calls (fast but limited size).  
- **Heap**: Stores dynamically allocated memory like objects (larger but slower).  
- Both are essential for managing memory during program execution.

## 7. Div Tag in HTML
The `<div>` tag is a **block-level element** that groups content.  
It is mainly used for layout and styling with CSS, or dynamic manipulation with JavaScript.

Example:  
```html
<div class="box">
  <h2>Title</h2>
  <p>This is inside a div.</p>
</div>
```

## 8. Aggregate Functions in SQL
Aggregate functions summarize large amounts of data into meaningful results.

- **COUNT()** → Counts rows.  
- **SUM()** → Adds values.  
- **AVG()** → Finds average.  
- **MIN()** → Finds minimum.  
- **MAX()** → Finds maximum.  

Example:  
```sql
SELECT AVG(salary), MAX(salary), MIN(salary) FROM employees;
```

## 9. Void Elements in HTML
Void elements are tags that don’t need closing tags and cannot have child elements.  
They are self-contained.

Examples:  
- `<br>` → Line break  
- `<img>` → Image  
- `<input>` → Input field  
- `<hr>` → Horizontal rule  
