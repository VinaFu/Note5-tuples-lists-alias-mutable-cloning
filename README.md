# Note5-variables

TOPICS:

  introduce new compound data types
    • tuples
    • lists
  idea of aliasing
  idea of mutability
  idea of cloning

1. TUPLES (元组)

    1.1 an ordered sequence of elements, can mix element types
  
    1.2 cannot change element values, IMMUTABLE
  
    1.3 represented with parentheses（括号）
  
    1.4 used to return more than one value from a function
  
   SWAP: (x,y)=(y,x)
   
   MANIPULATING TUPLES:
   
        def get_data(aTuple):
            nums = ()    # empty tuple
            words = ()
            for t in aTuple:
                # concatenating with a singleton tuple
                nums = nums + (t[0],)
                # only add words haven't added before
                if t[1] not in words:
                    words = words + (t[1],)
            min_n = min(nums)
            max_n = max(nums)
            unique_words = len(words)
            return (min_n, max_n, unique_words)

        test = ((1,"a"),(2, "b"),
                (1,"a"),(7,"b"))
        (a, b, c) = get_data(test)
        print("a:",a,"b:",b,"c:",c)

         #a: 1 b: 7 c: 2# 和之前return的内容一致：最大、最小、一共出现了几个字母（2）




