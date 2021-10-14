# Twice as old
Your function takes two arguments:

1. current father's age (years)
2. current age of his son (years)
Сalculate how many years ago the father was twice as old as his son (or in how many years he will be twice as old).
# Solution
```
int twice_as_old(int dad, int son) {
  return abs(dad-son*2);
}
```