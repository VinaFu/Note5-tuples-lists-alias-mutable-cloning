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
                    words = words + (t[1],)  #每个tuple里面都是0，1开始的，这里的1指得是第二位字母位
            min_n = min(nums)
            max_n = max(nums)
            unique_words = len(words)
            return (min_n, max_n, unique_words) # 分别取值，nums = （1，2，1，7）；words=（a,b）不取重

        test = ((1,"a"),(2, "b"), (1,"a"),(7,"b"))
        (a, b, c) = get_data(test)
        print("a:",a,"b:",b,"c:",c)

         #a: 1 b: 7 c: 2# 和之前return的内容一致：最大、最小、一共出现了几个字母（2）

        建立上述function之后，可以运用到其它方面去，比如，看Taylor在一定年限里给多少人写过歌，重名可缩减：
        
              def get_data(aTuple):
                  nums = ()    # empty tuple
                  words = ()
                  for t in aTuple:
                      nums = nums + (t[0],)
                      if t[1] not in words:
                          words = words + (t[1],)
                  min_n = min(nums)
                  max_n = max(nums)
                  unique_words = len(words)
                  return (min_n, max_n, unique_words)

              tswift = ((2014,"Katy"),
                        (2014, "Harry"),
                        (2012,"Jake"),
                        (2010,"Taylor"),
                        (2008,"Joe"))
              (min_year, max_year, num_people) = get_data(tswift)
              print("From", min_year, "to", max_year,  "Taylor Swift wrote songs about", num_people, "people!")


