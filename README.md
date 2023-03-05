# QuickSort-algorithm-in-AutoIt
QuickSort algorithm in AutoIt


```autoit
; define the QuickSort function
Func QuickSort(ByRef $arr, $left, $right)
    Local $i = $left, $j = $right
    Local $pivot = $arr[Int(($left + $right) / 2)]
    ; partition the array
    While $i <= $j
        While $arr[$i] < $pivot
            $i += 1
        WEnd
        While $arr[$j] > $pivot
            $j -= 1
        WEnd
        If $i <= $j Then
            Local $temp = $arr[$i]
            $arr[$i] = $arr[$j]
            $arr[$j] = $temp
            $i += 1
            $j -= 1
        EndIf
    WEnd
    ; recursive calls on sub-arrays
    If $left < $j Then QuickSort($arr, $left, $j)
    If $i < $right Then QuickSort($arr, $i, $right)
EndFunc

; example usage
Local $arr[10] = [5, 1, 9, 3, 7, 6, 2, 8, 4, 0]
QuickSort($arr, 0, UBound($arr) - 1)
MsgBox(0, "", "Sorted array: " & $arr)

```
