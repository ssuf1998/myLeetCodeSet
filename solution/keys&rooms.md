# [841. 钥匙和房间](https://leetcode-cn.com/problems/keys-and-rooms/)

```javascript
/**
 * @param {number[][]} rooms
 * @return {boolean}
 */
const canVisitAllRooms = (rooms) => {
    let visited = new Array(rooms.length).fill(false);
    visited[0] = true;

    let q = rooms[0];

    while (q.length) {
        let room = q.shift();
        if (!visited[room]) {
            visited[room] = true;
            q.push(...rooms[room]);
        }
    }

    return visited.every(b => b === true);
};
```

2020/8/31 14:43