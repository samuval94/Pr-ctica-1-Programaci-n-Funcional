-- remData es una función que filtra los elementos de una lista, dejando únicamente los que están dentro del intervalo dado [a, b].
-- Input:
-- [Int], lista inicial de números enteros.
-- Int, entero que indica el límite inferior del intervalo.
-- Int, entero que indica el límite inferior del intervalo.
-- 
-- Output: 
-- [Int], lista de números los cuales estaban en la lista inicial y estaban dentro del intervalo [a, b].
remData :: [Int] -> Int -> Int -> [Int]
remData [] _ _ = [] -- Condición de stop: si la lista es vacía, la lista resultante también lo será.
remData (x:xs) a b
  | x >= a && x <= b = x : remData xs a b -- Si el número cumple la siguiente condición: a <= x <= b, el número se conserva en la lista resultante
  -- y seguimos analizando el resto de la lista
  | otherwise = remData xs a b -- si esto no sucede, es descartado y se procede a analizar el resto de la lista.
  
main :: IO ()
main = do
  let lista = [1, 2, 3, 4, 5]
  let inferior = 0
  let superior = 3
  print (remData lista inferior superior)
