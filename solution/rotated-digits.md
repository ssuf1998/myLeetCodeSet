# [788. 旋转数字](https://leetcode-cn.com/problems/rotated-digits/)

```javascript
/**
 * @param {number} N
 * @return {number}
 */
const rotatedDigits = (N) => {
    let count = 0;
    for (let i = 1; i <= N; i++) {
        let num = i;
        let good_count = 0;
        let bad_count = 0;

        do {
            let d = num % 10;
            if (d === 2 || d === 5 || d === 6 || d === 9) {
                good_count++;
            }
            if (d === 3 || d === 4 || d === 7) {
                bad_count++;
            }
        } while ((num = ~~(num / 10)));

        if (bad_count === 0 && good_count >= 1) {
            count++;
        }
    }
    return count;
};
```

2020/8/31 16:21，这是个什么傻题