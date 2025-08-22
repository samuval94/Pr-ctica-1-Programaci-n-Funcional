remData :: [Int] -> Int -> Int -> [Int]
remData [] _ _ = []
remData (x:xs) a b
  | x >= a && x <= b = x : remData xs a b
  | otherwise = remData xs a b 
  
main :: IO ()
main = do
  let lista = [1, 2, 3, 4, 5]
  let inferior = 0
  let superior = 3
  print (remData lista inferior superior)
