spiror
======

Overview 
======

   Spiror is an new objective programing language that was based on 'EcmaScript' specification. Spiror compiler would 
translate the spiror codes to the standard javascript codes at the runtime (JIT compiler), so the spiror language could
works on any javascript platforms(Webbrowser,Mozilla rhino, Nodejs ...).

   We also find the javascript programing language workds hardly with OOP,  some example as below:
   
   In the java platform:
   
      class Sample extends Base {
         private String name;
      
         public void func() {
         //
         }
      }
   
   
   But in the javascript, we would write the ugly codes :
   
      function Sample () {
      }
   
      // Inherited
      Sample.prototype = new Base();
   
      // fields
      Sample.prototype.name = "";
   
      // shared method
      Sample.prototype.func = function() {
      };
    
  
   So I wanna provide an easy-OOP script language to enhance the standard javascript programing language.  spiror 
programing language features as below:

1. Strongly OOP as java style
   
   
  
