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
    
  
   So I wanna provide an easy-OOP script language to enhance the standard javascript programing language. 

      /* begin */
      @package cn.spiror.sample;

      @import cn.spiror.common.Base;
      
      /*
       * Class definition and inherited 
       */
      @class Sample : cn.spiror.common.Base {
         /* define an standard field */
         @property var name = null;
         
         @function func() {
            // standared javascript object defination
            var returns = {
               name : 'sample',
               op : function() {
                  // bala bala ....
               }
            };
            return returns;
         }
         @endfunction
      }
      @endclass
   
  
  
Features 
======
  1. Spiror is also as javascript application:   spiror programing codes will be compiled to the standard javascript
     codes and loaded on the underlined javascript engine (WebBrowser,Nodejs...);
  2. Portable
  3. Easily
  4. OOP inmediately
  
How spiror works
======

  1. Initializing spiror JIT compiler:
  2. Load your specified entry class:
  
      var classloader = spiror.lang.ClassLoaderFactory.getAvailableClassLoader();

      /**
       * Loading the specified 'cn.spiror.sample.Sample' with 4 steps:
       * 1. Test if the specified class already loaded. if already loaded the returns the exist handle, else gose
       *    to the next step;
       * 2. Load cn/spiror/sample/Sample.m on the classpath;
       * 3. Translate to loaded codes to the standard javascript codes;
       * 4. eval() it to the script engine runtimes.
       */
      classloader.loadClass("cn.spiror.sample.Sample");

      var o = new cn.spiror.sample.Sample();
      
      // launch the application
      o.main();
