React creates **Virtual DOM (a copy of actual browser DOM).**  

Virtual DOM is representation of actual DOM.

React uses **Diffing Algorithm (React Fiber - introduced in React 16)** to find difference between original Virtual DOM and updated Virtual DOM. 

After getting the difference React updates only those nodes which are updated in real DOM.

**Q: What is the reconciliation algorithm in React?**

A: The reconciliation algorithm is React's way of efficiently 
updating the DOM when the application's state changes. It compares the 
current component tree (virtual DOM) with the new one, calculates the 
differences (diff), and then makes the necessary updates to the actual 
DOM.

**Q: How does React decide which updates to perform first?**

A: React prioritizes updates based on their importance. High-priority
 updates, such as those triggered by user interactions, are processed 
before lower-priority updates like network requests. This helps ensure a
 smooth and responsive user experience.

**Q: What is the role of keys in reconciliation?**

A: Keys are used to uniquely identify child elements within a 
component. By assigning a unique key to each child, React can quickly 
identify which elements have changed, and which can be reused, making 
the reconciliation process more efficient.

**Q: How can I optimize the reconciliation process in my React application?**

A: Some best practices to optimize reconciliation include assigning 
unique keys to list items, avoiding unnecessary renders using `React.memo` or `shouldComponentUpdate`, and minimizing component complexity by breaking down complex components into smaller pieces.

Good resource to understand -

https://www.youtube.com/watch?v=MPCVGFvgVEQ&list=PLu71SKxNbfoDqgPchmvIsL4hTnJIrtige&index=6