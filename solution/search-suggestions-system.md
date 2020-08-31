# [1268. 搜索推荐系统](https://leetcode-cn.com/problems/search-suggestions-system/)

```javascript
/**
 * @param {string[]} products
 * @param {string} searchWord
 * @return {string[][]}
 */
const suggestedProducts = (products, searchWord) => {
    let suggest_list = [];
    for (let i = 0; i < searchWord.length; i++) {
        let search_word_sub = searchWord.slice(0, i + 1);
        let p_list = [];
        for (let p of products) {
            let p_sub = p.slice(0, i + 1);
            if (p_sub === search_word_sub) {
                p_list.push(p);
            }
        }
        suggest_list.push(p_list.sort().slice(0, 3));
    }

    return suggest_list;
};
```

2020/8/31 20:27