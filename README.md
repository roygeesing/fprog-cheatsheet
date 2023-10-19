# Types
```haskell
-- enum
data Color = Red | Yellow | Green
-- type synonym
type Coord = (Int, Int)
-- record
data Person = MkPerson { name :: String, age :: Int } deriving (Show)
```

| type class | methods |
| - | - |
| `Eq` | `==`, `/=` |
| `Ord` | `<`, `<=`, `>`, `>=`, `min`, `max` |
| `Show` | `show :: a -> String` |
| `Num` | `+`, `-`, `*`, `negate`, `abs`, `signum` |
| `Integral` | `div`, `mod` |
| `Fractional` | `/`, `recip` |


# Lists
```haskell
list :: [Char]
list = ['a', 'b', 'c', 'd']
head list = 'a'
tail list = ['b', 'c', 'd']
init list = ['a', 'b', 'c']
last list = 'd'

['a', 'b'. 'c'] = 'a' : ('b' : ('c' : []))

stdMatch :: Show a = [a] -> String
stdMatch [] = "Matched empty list"
stdMatch (x:xs) = "Mathced list with head " ++ show x
stdMatch (x:y:xs) = "Matched list starting with " ++ show x ++ ", " ++ show y

filter :: (a -> Bool) -> [a] -> [a]
map :: (a -> b) -> [a] -> [b]
```


# Functions
```haskell
-- case expression
describeList :: [a] -> String
describeList xs = "The list is " ++ case xs of
    []  -> "empty"
    [x] -> "a singleton list"
    xs  -> "a longer list"

abs :: (Num a, Ord a) => a -> a
-- guard
abs n
    | n < 0     = -n
    | otherwise = n

-- conditional expression
abs n = if n < 0 then -n else n

-- lambdas
incAll :: [Int] -> [Int]
incAll xs = map (\x -> x + 1) inc
```
