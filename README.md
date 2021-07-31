#Simple Balanced Parentheses

Balanced parentheses means that each opening symbol has a corresponding closing symbol and the pairs of parentheses are properly nested.

~~~javascript

class Validator {
    constructor(exp) {
        this.exp = exp;
        this.stack = []
    }

    isOpen(char) {
        return char === '('
    }
    isClose(char) {
        return char === ')'
    }
    isStackEmpty() {
        return this.stack.length === 0
    }
    validate() {
        for (let char of this.exp) {
            if (this.isOpen(char)) {
                this.stack.push(char)
            } else if (this.isClose(char)) {
                if (this.isStackEmpty()) {
                    return false
                } else {
                    this.stack.pop()
                }
            }

        }
        return this.isStackEmpty()
    }
}
const fun = new Validator('(()=>{})()')
console.log(fun.validate());
~~~
