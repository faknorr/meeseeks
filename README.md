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
