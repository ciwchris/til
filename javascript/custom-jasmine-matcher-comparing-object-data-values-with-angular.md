Custom Jasmine Matcher Comparing Object Data Values With Angular
================================================================

When verifying an object using the standard Jasmine watcher `toEqual` it performs a comparison
against all properties of the object, including properties which are functions. This causes the
verification to always fail. To only verify the properties containing values `angular.equal`, which
ignores functions when checking equality, can be used within a custom matcher.

```javascript
jasmine.addMatchers({
    toEqualPropertyValues: function() {
        return {
            compare: function(actual, expected) {
                return {
                    pass: angular.equals(actual, expected)
                }
            }
        }
    }
});
```

Then custom matcher is defined within the `beforeEach` function of a `describe` function. The custom
matcher will only be available to tests within that `describe` function. It can be used just like
the standard matchers:

```javascript
expect(result).toEqualPropertyValues(expected);
```
