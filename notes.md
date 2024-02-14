# Look at documentation more
## COMMIT OFTEN
GitHub helps you to keep track of work and not die if your computer does
Notes mostly based off CS 260 stuff

## Starting to set up stuff

### IP Address
- 52.1.193.26 public IP
- made it elastic for if i restart or turn off website so ip won't change
- This command to remote shell into server. Brings you to console window for the web server you just launched, ubuntu user's home directory: ssh -i [key pair file] ubuntu@[ip address]
- Keep key pair safe. Don't make it public. 

### Get a domain name
- subdomain * in dns records lets you do anything.domain.click
- must respond to confirmation email
- hbookshelf.click

### Caddy
- listens for incoming HTTP requests and serves up requested static files or routes request to another service
  - ability to route requests is gateway or reverse proxy
- serves up all your static HTML, CSS, and JavaScript files
- Configuration file: ~/Caddyfile contains the definitions for routing HTTP requests that Caddy receives. Do not manually edit except domain name
- HTML files: ~/public_html directory of files for when request made

### HTTPS
- make it secure by editing caddy file
- in console do this:
  - ssh -i [key pair file] ubuntu@[yourdomainnamehere]
  - cd ~
  - vi Caddyfile
  - in the file, edit it so :80 (port 80 for to process as http) is replaced with domain and subdomains also have your domain
  - save and exit vi with :wq
  - restart caddy so changes can take effect with sudo service caddy restart
- Let's Encrypt does the work of sending the web certificate proving it's the requester. User, https request, web server do web cert request, (verification) Let's Encrypt issue web certificate


## HTML
- head isn't supposed to be seen
### tags
- menu is alternative to ul that represents interaction
- nav is navigation element
### paragraph formatting tags
- hr in < /> adds horizontal line across page to break up sectons
- br is line break

## CSS

## JavaScript
- console.log('this will get printed to console')
- let is an object type you should use
- const is object type you can't reasssign location, but can if its array add to it for example
- falsy (false, 0, -0, '', NaN, null, undefined)
- truthy = !falsy
- when comparing two objects, compares memory locations not values in objects
- for(let i = 1; i<3; i++)
- while(bool statement), can get out of loop using break;
- switch statement, need break statement inside so it doesn't run all
  - kinda like if statements 
  - default happens if none of the other cases fit
  - example
    - switch(expression) {
        case x:
          // code block
          break;
        case y:
          // code block
          break;
        default:
          // code block
      }
    - switch expression evaluated once, value of expression is compared with the values of each case, if match associated code block is executed, if no match default code block executed
- anonymous function f = function (i) {return i;}, can later call f 
- arrowFunctions (like lambda)
  - single line with implicit return, inherits this binding
  - const arrow = () => 1;
  - const arrowWith BLock = (a) => {return a;}; must have return statement with {}
  - arrow functions are always anonymous
- closure function
  - uses stuff passed in in previous function call
  - remembers when function was created and enviornment it was created it
- strings
  - string literal syntax or string object
  - lots of operators: upper & lower case (toUpperCase(), toLowerCase()), split (split splits at parameter and makes list), endsWith (bool says if it ends with parameter), replace (par1 replaced with par2), slice (return par1 start to par2 end)
  - String('words')
  - RegExp('cat.?','i'), text.match(literalRegex), regex with flags /(dog)|(cat)|(bird)/gim, text.match, text.replace, var.test(text)
  - 'words'
- Array
  - arr = []
  - arr[1] gives element 1
  - arr.slice(2,5) pulls out part of arr
  - arr.length returns length
  - for(let entry of numbers) {loop over each element}
- Array Operations: doesn't change origial, just returns things
  - arr.map((n) => n * 100) map from some array to another with performing a function (every value*100 in newly returned array)
  - arr.reduce((a,c) => a+c) reduce contents of array to a single value, c is current value, a is accumulation value, 
    - starts with a as arr[0] and c as arr[1]
    - third parameter lets you specify what you want it to start with
  - arr.forEach((n) => n%2) does parameter function on each value in arr?
  - arr.filter((n)=>n%2)
  - arr.some((n)=>n%5)
- Exceptions
  - try block, do operations inside
  - catch(error){console.log('error: '+error)}, happens if try block throws any errors
  - finally, executes at end no matter what happens (try or catch)
- special operators
  - nullish is null of undefined, null is coalescing operator
    - z ?? (z=x); if z is nullish, set z=x
    - y ??=30, if y is nullish, set it to 30
- objects
  - let obj = {animal: 'fish',}
    - obj.count = 3, assigns count:3 to object
    - obj.location(cities: ['utah,'new york'], origin:'ocean')
  - can iterate over all properties for(const property in obj)
  - get object values, Object.keys(obj)
- spread