# Sharing content review code


## Table of Contents

[**1. Review content (En)** ](#1-Review-content-vi)


<br>

## 1. Review content (En)

### The content of code reviews is usually evaluated based on the project's rules first, and then the company's rules are considered afterward.

* [1.1 Check branch name (depend on project's rule)](#1.1)
* [1.2 The commit message content should be written in English and explicit](#1.2)
* [1.3 Check ignored files](#1.3)
* [1.4 When adding a new file, it must follow the same convention as the similar files in the project](#1.4)
* [1.5 Require merge into object branch is correct](#1.5)
* [1.6 Number of commit files](#1.6)
* [1.7 When creating a new function, check if it exists or can modify an existing function](#1.7)
* [1.8 Pay attention when adding new Env variables](#1.8)
* [1.9 Check package.json & .lock](#1.9)
* [1.10 Be aware when common functions are modified](#1.10)
* [1.11 Don't commit secret information such as Secret Key, Access Key etc](#1.11)
* [1.12 Using Enum, CONST, .config etc to express a value](#1.12)
* [1.13 Using file .min(minify) when adding new library](#1.13)
* [1.14 Remove unuse code such as debugger, console.log etc](#1.14)

### Nodejs/Typescript

* [1.15 Avoid using the "any" type if it's possible to define the type of the target](#1.15)
* [1.16 Using lodash for processing collection](#1.16)
* [1.17 Using moment/day.js for processing Date/Time](#1.17)
* [1.18 Using Big.js / Math.js for processing Amount/Big number/Decimal number](#1.18)

### Common
* [1.19 Check performance for API search](#1.19)
* [1.20 API insert/update/delete multi records must use transaction/bulkUpdate/bulkInsert instead loop and process each one](#1.20)

### Review by company rules
https://github.com/BWV-Dev/bwv-coding-rules

### Review by project rules

Example, NodeJS/VueJS (Mr.Phi): <br> 
https://github.com/orgs/Briswell-Ltd/projects/4/views/1?pane=issue&itemId=12515593 <br>
https://github.com/orgs/Briswell-Ltd/projects/4/views/1?pane=issue&itemId=14294336


<table>

<tr id="1.1">
<td width="5%">

**1.1**
</td>
<td width="50%">
Check branch name</td>
<td width="45%">

```typescript
feature/issue-#####
```

</td>
</tr>

<tr id="1.2">
<td width="5%">

**1.2**
</td>
<td width="50%">
The commit message content should be written in English and explicit </td>
<td width="45%">

```typescript
Add new screen S301_1
or
Fixing bug cannot display items A B C
```

</td>
</tr>

<tr id="1.3">
<td width="5%">

**1.3**
</td>
<td width="50%">
Check ignored files</td>
<td width="45%">

```typescript
No need commit .env , ./dist
```

</td>
</tr>

</td>
</tr>

<tr id="1.4">
<td width="5%">

**1.4**
</td>
<td width="50%">
When adding a new file, it must follow the same convention as the similar files in the project</td>
<td width="45%">

```typescript
Example adding new controller, it must be named same as others
user.controller.ts
or
userController.ts
```

</td>
</tr>

<tr id="1.5">
<td width="5%">

**1.5**
</td>
<td width="50%">
Require merge into object branch is correct</td>
<td width="45%">

```typescript
Need to merge into Develop or Main or something
```

</td>
</tr>

<tr id="1.6">
<td width="5%">

**1.6**
</td>
<td width="50%">
Number of commit files</td>
<td width="45%">

```typescript
Some repos need to commit build files or not. Must check it.
```

</td>
</tr>


<tr id="1.7">
<td width="5%">

**1.7**
</td>
<td width="50%">
When creating a new function, check if it exists or can modify an existing function</td>
<td width="45%">

```typescript
Some functions can be customized for reuse, so consider instead creating a new function that makes the source bloat
Especially the functions in the file utils, common, middleware etc
```

</td>
</tr>

<tr id="1.8">
<td width="5%">

**1.8**
</td>
<td width="50%">
Pay attention when adding new Env variables</td>
<td width="45%">

```typescript
Be aware when adding new env
Is is necessary or affect some where
```

</td>
</tr>

<tr id="1.9">
<td width="5%">

**1.9**
</td>
<td width="50%">
Check package.json & .lock</td>
<td width="45%">

```typescript
Some cases, the .lock file has been changed miscellaneously. Need to check to make sure the package version is not wrong
```

</td>
</tr>

<tr id="1.10">
<td width="5%">

**1.10**
</td>
<td width="50%">
Be aware when common functions are modified</td>
<td width="45%">

```typescript
Functions that are used in multiple places are more likely to be affected and cause bugs degrade.
```

</td>
</tr>

<tr id="1.11">
<td width="5%">

**1.11**
</td>
<td width="50%">
Don't commit secret information such as Secret Key, Access Key etc</td>
<td width="45%">

```typescript
Because of security issue, shouldn't commit them
```

</td>
</tr>

<tr id="1.12">
<td width="5%">

**1.12**
</td>
<td width="50%">
Using Enum, CONST, .config etc to express a value</td>
<td width="45%">

```typescript
// Using Enum to express Status
export declare enum Status {
    '待機中' = 1,
    '起動中' = 2,
    '正常終了' = 3,
    '異常終了' = 4,
    '中断／強制終了' = 9
}
Bad way: status = 4
Good way: status = Status[異常終了]
```

</td>
</tr>

<tr id="1.13">
<td width="5%">

**1.13**
</td>
<td width="50%">
Using file .min(minify) when adding new library</td>
<td width="45%">

```typescript
// .min files have small size
Ex: jquery.min.js
```

</td>
</tr>

<tr id="1.14">
<td width="5%">

**1.14**
</td>
<td width="50%">
Remove unuse code such as debugger, console.log etc</td>
<td width="45%">

```typescript
Remove any redundant lines of code such as console.log, debugger, and any lines that are commented out.
```

</td>
</tr>

<tr id="1.15">
<td width="5%">

**1.15**
</td>
<td width="50%">
Avoid using the "any" type if it's possible to define the type of the target
</td>
<td width="45%">

```typescript
// Bad 
function sum2Number(first: any, second: any){
    return first + second;
}
// Good 👍
function sum2Number(first: number, second: number){
    return first + second;
}
```

</td>
</tr>


<tr id="1.16">
<td width="5%">

**1.16**
</td>
<td width="50%">
Using lodash for processing collection</td>
<td width="45%">

```typescript
// Bad 
function getActiveStudentFromList(studentLst: Student[]){
    return studentLst.filtler(x => x.deletedAt === null);
}

// Good 👍
function getActiveStudentFromList(studentLst: Student[]){
    return _.filter((x:Student) => x.deletedAt === null);
}
```

</td>
</tr>


<tr id="1.17">
<td width="5%">

**1.17**
</td>
<td width="50%">
Using moment/day.js for processing Date/Time</td>
<td width="45%">

```typescript
import moment from "moment";
import "moment-timezone";

// The library provides multiple functions that are more convenient and accurate
const getCurrentTimeJp = moment.tz("Asia/Tokyo").format('YYYY/MM/DD HH:mm:ss');
```

</td>
</tr>

<tr id="1.18">
<td width="5%">

**1.18**
</td>
<td width="50%">
Using Big.js / Math.js for processing Amount/Big number/Decimal number</td>
<td width="45%">

```typescript
// Javascript cannot handle big numbers and decimals correctly, need help from the library
let x = new Big(0.1);
let y = new Big(0.2);
console.log(x.add(y).toFixed()); // 0.3
```

</td>
</tr>


<tr id="1.19">
<td width="5%">

**1.19**
</td>
<td width="50%">
Check performance for API search</td>
<td width="45%">

```typescript
Usually do not select all columns
Do not select all from table and then filter
Make sure the number of queries is minimal
```

</td>
</tr>

<tr id="1.20">
<td width="5%">

**1.20**
</td>
<td width="50%">
API insert/update/delete multi records must use transaction/bulkUpdate/bulkInsert instead loop and process each one</td>
<td width="45%">

```typescript
// Bad 
async function insertProducts(products) {
  products.forEach(product => await Product.create(product))
}

// Good 👍
async function insertProducts(products, transaction) {
  const transaction = await sequelize.transaction();
  try {
    const insertedProducts = await Product.bulkCreate(products, { transaction });
    await transaction.commit();
    return insertedProducts;
  } catch (error) {
    await transaction.rollback();
    throw error;
  }
}
```

</td>
</tr>

</table>
