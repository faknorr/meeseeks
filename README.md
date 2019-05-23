# meeseeks
Bunch of Rick'n Morty quotes for Meeseeks

# Usage
git_ref=master
quotes=$(curl -sf https://raw.githubusercontent.com/faknorr/meeseeks/${git_ref}/quotes.txt || echo "")
max=$(echo -en "${quotes}" | tr \| "\n" | wc -l)
if [[ ${max} -gt 0 ]]; then
  rnd=$(( $[${RANDOM} % ${max} + 1 ] ))
  echo -e "${quotes}" | tr \| "\n" | sed "${rnd}q;d"
fi

# Check entropy of ${RANDOM} variable
> Note: useless knowledge
```
max=50
iterations=100000
for i in $(seq 1 ${iterations}); do echo $(( $[${RANDOM} % ${max} + 1 ] )); done | sort -n | uniq -c
```
Example result:
```
1954 1
2007 2
1969 3
2030 4
1919 5
2022 6
1991 7
2052 8
1997 9
1993 10
1982 11
1970 12
2019 13
1985 14
1991 15
1984 16
2107 17
1981 18
2002 19
2002 20
2019 21
1882 22
1979 23
2004 24
2064 25
2055 26
2053 27
2014 28
2073 29
1935 30
1962 31
2059 32
2039 33
1989 34
1991 35
2096 36
1952 37
1986 38
1974 39
1990 40
2003 41
1939 42
1951 43
1975 44
1942 45
2000 46
2012 47
2015 48
2074 49
2016 50
```

When the count of the numbers are close to each other we've a good entropy
