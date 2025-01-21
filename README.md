# MongoDB $inc operator error: incrementing a string field
This example demonstrates an incorrect usage of MongoDB's `$inc` operator. The `$inc` operator is designed to increment numeric fields. Attempting to use it on a string field will result in an error.  The solution shows the corrected approach.

## Bug
The bug lies in the following line:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: 'abc' } });
```
This code attempts to increment the `field` which is a string. 
## Solution
The solution involves ensuring that the `field` is of numeric type before using `$inc`.  If necessary, convert the field to a number before the update or handle the error gracefully.