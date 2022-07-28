# Note5-tuples-lists-alias-mutable-cloning

TOPICS:

  introduce new compound data types
    • tuples
    • lists
  idea of aliasing
  idea of mutability
  idea of cloning

1. TUPLES (元组) 

   和list很像，但是内部可以包含很多元素，比如内部再包含一个坐标，然后分别跑

    1.1 an ordered sequence of elements, can mix element types
  
    1.2 cannot change element values, IMMUTABLE
  
    1.3 represented with parentheses（括号）
  
    1.4 used to return more than one value from a function
  
   SWAP: (x,y)=(y,x)
   
   # MANIPULATING TUPLES（这个代码好看好多遍哦！！）:
   
        def get_data(aTuple):
            nums = ()    # empty tuple
            words = ()
            for t in aTuple:
                # concatenating with a singleton tuple
                nums = nums + (t[0],)
                # only add words haven't added before
                if t[1] not in words:
                    words = words + (t[1],)  #每个tuple里面都是0，1开始的，这里的1指得是第二位字母位。因为第一次只有t(0)所以没有它
            min_n = min(nums)
            max_n = max(nums)
            unique_words = len(words)
            return (min_n, max_n, unique_words) # 分别取值，nums = （1，2，1，7）；words=（a,b）不取重

        test = ((1,"a"),(2, "b"), (1,"a"),(7,"b"))
        (a, b, c) = get_data(test)
        print("a:",a,"b:",b,"c:",c)

         #a: 1 b: 7 c: 2# 和之前return的内容一致：最大、最小、一共出现了几个字母（2）
         可以用pythontutor看过程

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

2. LISTS

  2.1 ordered sequence of information, accessible by index
  
  2.2 a list is denoted by square brackets, []
  
  2.3 a list contains elements
  
      • usually homogeneous (ie, all integers)
      • can contain mixed types (not common)
  
  2.4 list elements can be changed so a list is MUTABLE，可通过index直接改value
  
  ADD: 
    L = [2,1,3]
    L.append(5) -> L is now [2,1,3,5]
    mutates the list
  
    Using concatenation, + operator, to give you a new list
    mutate list with L.extend(some_list)
        L1 = [2,1,3]
        L2 = [4,5,6]
        L3 = L1 + L2  -> L3 is [2,1,3,4,5,6]
        L1, L2 unchanged
        L1.extend([0,6]) -> mutated L1 to [2,1,3,0,6] 
  
  
   REMOVE:
   
          L = [2,1,3,6,3,7,0]          
          L.remove(2)会改变/mutate. 且2:是具体被移除的value          
          L.remove(3)是移除第一个3          
          del(L[1])移除第二位，也会mutate          
          L.pop() 移除最右，所以是去0
      
      
   CONVERT LISTS TO STRINGS AND BACK:
     
      convert string to list with list(s)
      can use s.split(), to split a string on a character paramete
 use ''.join(L) to turn a list of characters into a string, can
give a character in quotes to add char between every element
6.0001 LECTURE 5 14
s = "I<3 cs"  s is a string
list(s)  returns ['I','<','3',' ','c','s']
s.split('<')  returns ['I', '3 cs']
L = ['a','b','c']  L is a list
''.join(L)  returns "abc"
'_'.join(L)  returns "a_b_c"
   
   sorted sort? and P21?? 改不改？
   
   cone
   chill = cool [:] (0:len(cool))即引用所有
   
   nested - 嵌套 - 类似于复合函数
   
   
   
   
   
