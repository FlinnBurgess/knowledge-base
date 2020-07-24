# Labels & Selectors

### Labels

Labels are key-value pairs that you can attach to kubernetes objects, like pods. They are useful to help meaningful and relevant information about an object. You can label nearly anything.

Kubernetes provides a set of pre-defined labels, which you can find online, but you can also define your own labels.

### Selectors

Selectors are a means of selecting objects based on their labels. You can select objects by finding labels which are equal to a given value, or by finding labels which belong to a given set.

### Example of use

Let's say we have a number of nodes, only some of which use SSDs rather than HDDs. We can specify that an app only be deployed to nodes which contain an SSD so that our app will run as fast as necessary by using a selector to match the relevant tag.

