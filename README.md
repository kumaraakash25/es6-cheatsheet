# es6-cheatsheet

function test() {
    for(var temp = 0; temp < 5; temp++) {
        console.log(temp);
    }
    console.log(temp);
}

//test();
// Using a var will define the variable scope in the entire function

function test() {
    for(let x = 1; x < 4; x++) {
        console.log(x);
    }
    //console.log(x); // This will show an error on console 'x' is not defined
}

//test();
// Using let will restrict its scope inside the block

const y= 10;
//console.log(y);
//y =20;
//console.log(y);
// We cannot reassign a value to a constant variable, Assignment to constant variable, error in cosole

// Use const over let, use let only when you need to redefine

const person = {
    name: 'Aakash',
    age: 31,
    testPerson() {
        //console.log('Hi Person'+ this.name);
        console.log(this); // This returns a reference to the current object
    }
}
const nameKeyWord = 'name';
//console.log(person[nameKeyWord]);
//person.testPerson();

const test2 = Person.testPerson.bind(Person);
//test2();
// The reference to function is still a objet so we need to bind it with a valid object 

const function1 = function(number) {
    return number*number;
}
//console.log(function1(5));

// Using arrow function to do the exact similar stuff 
const function2 = (number) => number * number;
//console.log(function2(5));

const jobs = [
    {id: 1, isActive: true},
    {id: 2, isActive: true},
    {id: 3, isActive: false}
];

//console.log(jobs.filter(function(job) {return job.isActive}));
//console.log(jobs.filter((job) => job.isActive));

//jobs.map(job => console.log(job));

const address = {
    street: '281/17 Muwaiya',
    city: 'Luknow',
    country: 'India'
};

//const street = address.street;
//const city = address.city;
//console.log(street);
// To avoid this use the concept of Object destructuring 
const { country, street, city } = address;
//console.log(country);

const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const combinedArray = array1.concat(array2);
//console.log(combinedArray);
// Use the spread operator to expand aray and edit the array if required
const combinedArray2 = [...array1, 1000, ...array2];
//console.log(combinedArray2);

const object1 = {name: 'Aakash'};
const object2 = {interest: 'Software Development'};
const spreadCombine = {...object1, ...object2};
// console.log(spreadCombine);
// This does not put the object into an array but rather puts into single object

class Personell {
    constructor(name) {
        this.name = name;
    }
    walk() {
        console.log('Walk '+ this.name);
    }
}

const person1 = new Personell('aakash');
//person1.walk();
// define a class to use the blueprint further

class Teacher extends Personell {

    constructor(name, subject) {
        super(name);
        this.subject = subject;
    }
    teach() {
        console.log('Teach');
    }
}
const teacher1 = new Teacher('Aakash 2', 'Computer Science');
//teacher1.walk();

// since module is private by defalt to use this class in other modules use export class Person{
//    
//}
// To use this class 
// import {Person} from './person'

 import React, {Component} from 'react'
// React is default export, Component is named export React is defined something  export default class React {

//} Component is defined export class Component {
