# react-ass3

# Explain what is prototype and what is prototype chain in your own words

	•	Prototype is a mechanism in JavaScript.
	•	It allows objects to inherit properties and methods from other objects.
	•	Every JavaScript object has a prototype property.
	•	This property points to another object.
	•	Prototype chain is a series of linked prototypes.
	•	It’s how JavaScript objects inherit features.
	•	When looking for a property, JavaScript first checks the object itself.
	•	If not found, it checks the object’s prototype.
	•	This process continues up the chain until the property is found or the end of the chain is reached.
 
# Implement your versions of the following Array methods .
map, filter, reduce, every, find, includes, join, pop, push, reverse, slice, sort
-
1.map

      Array.prototype.myMap = function(callback) {
        let result = [];
        for (let i = 0; i < this.length; i++) {
          result.push(callback(this[i], i, this));
        }
        return result;
      };
2.filter 

      Array.prototype.myFilter = function(callback) {
        let result = [];
        for (let i = 0; i < this.length; i++) {
          if (callback(this[i], i, this)) {
            result.push(this[i]);
          }
        }
        return result;
      };


3. reduce

	    Array.prototype.myReduce = function(callback, initialValue) {
	          let accumulator = initialValue !== undefined ? initialValue : this[0];
	          let startIndex = initialValue !== undefined ? 0 : 1;
	          for (let i = startIndex; i < this.length; i++) {
	            accumulator = callback(accumulator, this[i], i, this);
	          }
	          return accumulator;
	        };

5. every

		   Array.prototype.myEvery = function(callback) {
		          for (let i = 0; i < this.length; i++) {
		            if (!callback(this[i], i, this)) {
		              return false;
		            }
		          }
		          return true;
		        };

6. find

	        Array.prototype.myFind = function(callback) {
	          for (let i = 0; i < this.length; i++) {
	            if (callback(this[i], i, this)) {
	              return this[i];
	            }
	          }
	          return undefined;
	        };

7. includes

		      Array.prototype.myIncludes = function(value) {
		        for (let i = 0; i < this.length; i++) {
		          if (this[i] === value) {
		            return true;
		          }
		        }
		        return false;
		      };

8. join

	      Array.prototype.myJoin = function(separator = ',') {
	        let result = '';
	        for (let i = 0; i < this.length; i++) {
	          result += this[i];
	          if (i < this.length - 1) {
	            result += separator;
	          }
	        }
	        return result;
	      };

9. pop

	        Array.prototype.myPop = function() {
	          if (this.length === 0) return undefined;
	          const lastElement = this[this.length - 1];
	          this.length = this.length - 1;
	          return lastElement;
	        };

10. push

		      Array.prototype.myPush = function(...elements) {
		        for (let i = 0; i < elements.length; i++) {
		          this[this.length] = elements[i];
		        }
		        return this.length;
		      };
		

11. reverse

		      Array.prototype.myReverse = function() {
		        let left = 0;
		        let right = this.length - 1;
		        while (left < right) {
		          let temp = this[left];
		          this[left] = this[right];
		          this[right] = temp;
		          left++;
		          right--;
		        }
		        return this;
		      };

12. slice

		      Array.prototype.mySlice = function(start = 0, end = this.length) {
		        let result = [];
		        for (let i = start; i < end; i++) {
		          if (i < this.length) {
		            result.push(this[i]);
		          }
		        }
		        return result;
		      };
13. sort
		
		  Array.prototype.mySort = function(compareFunction) {
			      for (let i = 0; i < this.length - 1; i++) {
			        for (let j = 0; j < this.length - 1 - i; j++) {
			          if (compareFunction ? compareFunction(this[j], this[j + 1]) > 0 : this[j] > this[j + 1]) {
			            let temp = this[j];
			            this[j] = this[j + 1];
			            this[j + 1] = temp;
			          }
			        }
			      }
			      return this;
			    };
	    
