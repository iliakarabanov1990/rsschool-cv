<img src="/files/MyPhoto.JPG" alt="my photo" style="width: 100px; height: auto; border-radius: 50%;padding: 5px">

    **Karabanov Ilia**

## My contacts:
    *phone: +375(33)353-11-19
    *email: iliaKarabanov@gmail.com

## About me:
    I have more than 10 years of experience in business automation in 1C. I want to improve and expand my developer skills and I have chosen a goal: to become a Salesforce developer.  

## My skills
    * 1c
    * Git
    * HTML
    * CSS
    * JS
    * TypeScript
    * Apex
    * SQL


## Code Examples

`class AsyncArray extends Array{ 
    serialMap(transformFunc){
        const func = _async(function* (arr){
            const newArr = new AsyncArray();
            for(let i=0; i<arr.length; i++){
                newArr[i] = yield transformFunc(arr[i], i, arr);
            }
            return newArr;
        });
            
        return func(this);         
    }
}

////////////////1 task/////////////////////////////////////////////////
const asyncArray = new AsyncArray(1, 2, 5, 7, 12);
asyncArray.serialMap(asyncTransformation)
     .then(result => result.forEach((element) => console.log(element)));

////////////////2 task/////////////////////////////////////////////////
const testFunction = _async(function* (a, b, c) {
    return ((yield someAsyncAction(a)) + (yield oneMoreAsyncAction(b))) / (yield oneMoreAsyncAction(c));
});

testFunction(2, 3, 1).then(a => console.log(a));

export function _async(genFunc){  
    return (...params) => new Promise(resolve => {
        const gen = genFunc(...params);
        const func = (v) => {
            const r = gen.next(v);
            if (!r.done) r.value.then(func);
            else resolve(r.value);
        }
        func();
    })
}
////////////////for 1 task/////////////////////////////////////////////////
export const asyncTransformation = (el, index, asyncArray) => {
    return new Promise((resolve) => {setTimeout(() => resolve(el*2), 2*1000)})
};
////////////////for 2 task/////////////////////////////////////////////////
export const someAsyncAction = (el) => {
    return new Promise((resolve) => {setTimeout(() => resolve(el*2), 1*1000)})
};

export const oneMoreAsyncAction = (el) => {
    return new Promise((resolve) => {setTimeout(() => resolve(el*2), 2*1000)})
};`

## Work Experience

1. 1 year 1c 'CRM'
2. 3 years 1c 'Trade management' 
3. 7 years 1c 'Accounting', 1c 'Salary and personnel management', Data exchanges.

## Education (including completed courses and training)

1. 
## English Language: 
    A2-B1


