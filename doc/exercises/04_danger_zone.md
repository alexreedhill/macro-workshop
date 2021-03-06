# Danger Zone

## Multiple evaluation

1. Multiple evaluation isn't always a bug. In fact, in many cases it's the
   fundamental reason for a macro existing. Give a couple of example macros in
   clojure.core that may evaluate one or more of their input expressions
   multiple times.

2. Look back at your solutions to the exercises so far, and see whether you've
   got any multiple evaluation problems. Looking for an unquote in front of the
   same symbol in multiple places is usually a good clue.

3. Why can't I take the value of a macro? Is it a Clojure compiler limitation?
   Or something more fundamental?

4. Isn't there a trick we can do to avoid using a macro to implement `log-row`?
   (still building on top of `log`)

    ```clojure
    (defmacro log [& args]
     `(println (str "[INFO] " (string/join " | " ~(vec args)))))

    (log-row ["column one" "column two" "column three"])
    ```

   Why or why not? Hint: could the fact that we have `eval` help?


