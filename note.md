# shell script 笔记 

## 判断是否存在这个命令

```bash
existCmd() {
  cmd=$1
  if type $cmd >/dev/null 2>&1; then
    echo "exist $cmd"
  else
    echo "no exist $cmd"
  fi
}
```


## 多选项

```bash
testCase() {
  echo '输入 1 到 4 之间的数字:'
  echo -n '你输入的数字为:'
  read aNum
  case $aNum in
      1)  echo '你选择了 1'
      ;;
      2)  echo '你选择了 2'
      ;;
      3)  echo '你选择了 3'
      ;;
      4)  echo '你选择了 4'
      ;;
      *)  echo '你没有输入 1 到 4 之间的数字'
      ;;
  esac
}
```


## forloop

```bash
testArray() {
  test_array=(test1 test2 "test3" test4)
  for i in ${test_array[@]}; do
    echo "array element is ${i}"
  done
  ## echo "array elements are ${test_array[*]}"
}
```

## 传递数组参数

```bash
bar=(
	bar1
	bar2
	bar3
)

foo() {
	array=$1

	for i in ${array[*]}; do
		echo $i
	done
}

foo "${bar[*]}"
```
