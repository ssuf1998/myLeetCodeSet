# [54. 螺旋矩阵](https://leetcode-cn.com/problems/spiral-matrix/)

```javascript
/**
 * @param {number[][]} matrix
 * @return {number[]}
 */
const spiralOrder = (matrix) => {
    if (matrix.length === 0 || matrix[0].length === 0) {
        return [];
    }

    let top = 0, right = matrix[0].length - 1,
        bottom = matrix.length - 1, left = 0;
    let ret = [];

    // > 0, v 1, < 2,^ 3
    let direct = 0;

    while (ret.length !== matrix.length * matrix[0].length) {
        switch (direct) {
            case 0: {
                ret.push(...(matrix[top].slice(left, right + 1)));
                top += 1;
                direct = 1;
                break;
            }
            case 1: {
                for (let r = top; r <= bottom; r++) {
                    ret.push(matrix[r][right]);
                }
                right -= 1;
                direct = 2;
                break;
            }
            case 2: {
                ret.push(...(matrix[bottom].slice(left, right + 1).reverse()));

                bottom -= 1;
                direct = 3;
                break;
            }
            case 3: {
                for (let r = bottom; r >= top; r--) {
                    ret.push(matrix[r][left]);
                }
                left += 1;
                direct = 0;
                break;
            }
        }
    }
    return ret;
};
```

2020/8/31 14:52