---
title: "코딩 테스트 문제"
date: 2020-08-03 16:32:00 +0900
categories: codingtest
---

https://programmers.co.kr/learn/courses/30/lessons/60057?language=javascript
100 점

```
const zipByWordCount = function(s, wordCount) {
    let answerStr = '';

    let originStr = ''
    let matchStr = ''
    let count = 1;
    for(let i = 0 ; i < s.length ; i += wordCount) {
        originStr = s.substring(i, i + wordCount)
        matchStr = s.substring(i + wordCount, i + wordCount + wordCount)

        if (originStr === matchStr) {
            count += 1;
        } else if (count === 1) {
            answerStr += `${originStr}`
            count = 1;
        } else {
            answerStr += `${count}${originStr}`
            count = 1;
        }
    }

    return answerStr
}

function solution(s) {
    var answer = s.length;
    let answerStr = '';
    let len = s.length / 2;
    if (len % 1 === 0) {
        len += 1;
    }
    for(let i = 1; i < len ; i += 1) {
        answerStr = zipByWordCount(s, i)
        answer = Math.min(answer, answerStr.length)
    }

    return answer;
}
```

https://programmers.co.kr/learn/courses/30/lessons/60058
12 점 실패

```
// 균형잡힌 괄호 문자열
const isBalance = function(p) {
    return (p.match(/\(/) || []).length === (p.match(/\)/) || []).length
}

// 올바른 괄호 문자열
const isCorrect = function(p) {
    const arr = p.split('')
    let stack = []

    for(let i = 0 ; i < arr.length ; i += 1) {
        if (arr[i] === '(') {
            stack.push('(')
        } else {
            if (stack.pop() !== '(') {
                return false;
            }
        }
    }

    return stack.length === 0;
}

const change = function(p) {
    return p
        .substring(1, p.length - 1)
        .split('')
        .map((w) => w === '(' ? ')' : '(')
        .join('')
}

function solution(p) {
    var answer = '';
    if ('' === p) return '';
    // if (isCorrect(p)) return p;
    let u = '';
    let v = '';
    let find = false
    for(let i = 2 ; i <= p.length ; i += 2) {
        u = p.substring(0, i)
        if (isBalance(u)) {
            find = true;
        }

        if (find) {
            v = p.substring(i)

            if (isCorrect(u)) {
                v = solution(v)
            } else {
                if (v === '') {
                    return `()${change(u)}`
                } else {
                    return '(' + solution(v) + ')' + change(u)
                }
            }
            break;
        }
    }

    answer = u + v;
    return answer;
}
```

https://programmers.co.kr/learn/courses/30/lessons/60059
91 점

```
// 시계 방향 90도
const rotation90 = function(key) {
    let result = [];
    for(let i = 0; i < key.length ; i += 1) {
        result.push([])
    }
    for(let i = 0; i < key.length ; i += 1) {
        for(let j = 0 ; j < key[i].length ; j += 1) {
            result[j][key.length - i - 1] = key[i][j]
        }
    }
    return result;
}

const print = function(key) {
    console.log(
        '=====\n' + key.map((col = []) => col.join(',')).join('\n')
    )
}

const getExtendLock = function(lock) {
    const iLen = lock.length;
    const jLen = lock[0].length;

    let extendLock = [];
    for(let i = 0; i < iLen ; i += 1) {
        extendLock.push(new Array(jLen * 3))
    }

    for(let i = 0; i < iLen ; i += 1) {
        let emptyArr = new Array(jLen * 3);
        for(let j = 0 ; j < lock[i].length ; j+= 1) {
            emptyArr[jLen + j] = lock[i][j];
        }
        extendLock.push(emptyArr);
    }

    for(let i = 0; i < iLen ; i += 1) {
        extendLock.push(new Array(jLen * 3))
    }
    return extendLock;
}

const getLockCount = function(lock) {
    return lock.map((col) => col.join('')).join('').match(/0/g).length
}

const match = function(key, extendLock, iMove, jMove, lockCount) {
    let count = 0;
    for(let i = 0 ; i < key.length ; i += 1) {
        for(let j = 0 ; j < key[0].length ; j += 1) {
            let row = extendLock[i + iMove][j + jMove]
            if (row === 1 && 1 === key[i][j]) return false;
            if (row === 0 && 1 === key[i][j]) {
                count += 1;
                if (lockCount < count) {
                    return false;
                }
            }
        }
    }

    return lockCount === count;
}

function solution(key, lock) {
    var answer = true;

    let key90 = rotation90(key)
    let key180 = rotation90(key90)
    let key270 = rotation90(key180)

    const extendLock = getExtendLock(lock)
    const lockCount = getLockCount(lock)

    for (let i = 0 ; i < lock.length * 2 ; i += 1) {
        for(let j = 0; j < lock[0].length * 2 ; j += 1) {
            if (match(key, extendLock, i, j, lockCount)) {
                return true;
            }

            if (match(key90, extendLock, i, j, lockCount)) {
                return true;
            }

            if (match(key180, extendLock, i, j, lockCount)) {
                return true;
            }

            if (match(key270, extendLock, i, j, lockCount)) {
                return true;
            }
        }
    }

    return false;

    return answer;
}
```

100 점

```
// 시계 방향 90도
const rotation90 = function(key) {
    let result = [];
    for(let i = 0; i < key.length ; i += 1) {
        result.push([])
    }
    for(let i = 0; i < key.length ; i += 1) {
        for(let j = 0 ; j < key[i].length ; j += 1) {
            result[j][key.length - i - 1] = key[i][j]
        }
    }
    return result;
}

const print = function(key) {
    console.log(
        '=====\n' + key.map((col = []) => col.join(',')).join('\n')
    )
}

const getExtendLock = function(lock) {
    const iLen = lock.length;
    const jLen = lock[0].length;

    let extendLock = [];
    for(let i = 0; i < iLen ; i += 1) {
        extendLock.push(new Array(jLen * 3))
    }

    for(let i = 0; i < iLen ; i += 1) {
        let emptyArr = new Array(jLen * 3);
        for(let j = 0 ; j < lock[i].length ; j+= 1) {
            emptyArr[jLen + j] = lock[i][j];
        }
        extendLock.push(emptyArr);
    }

    for(let i = 0; i < iLen ; i += 1) {
        extendLock.push(new Array(jLen * 3))
    }
    return extendLock;
}

const match = function(key, extendLock, iMove, jMove, lockCount) {
    let count = 0;
    for(let i = 0 ; i < key.length ; i += 1) {
        for(let j = 0 ; j < key[0].length ; j += 1) {
            let row = extendLock[i + iMove][j + jMove]
            if (row === 1 && 1 === key[i][j]) return false;
            if (row === 0 && 1 === key[i][j]) {
                count += 1;
                if (lockCount < count) {
                    return false;
                }
            }
        }
    }

    return lockCount === count;
}

const getLockCount = function(lock) {
    let count = 0;

    return (lock.map((col) => col.join('')).join('').match(/0/g) || []).length
}

function solution(key, lock) {

    var answer = true;

    let key90 = rotation90(key)
    let key180 = rotation90(key90)
    let key270 = rotation90(key180)

    const extendLock = getExtendLock(lock)
    const lockCount = getLockCount(lock)

    for (let i = 0 ; i < lock.length * 2 ; i += 1) {
        for(let j = 0; j < lock[0].length * 2 ; j += 1) {
            if (match(key, extendLock, i, j, lockCount)) {
                return true;
            }

            if (match(key90, extendLock, i, j, lockCount)) {
                return true;
            }

            if (match(key180, extendLock, i, j, lockCount)) {
                return true;
            }

            if (match(key270, extendLock, i, j, lockCount)) {
                return true;
            }
        }
    }

    return false;

    return answer;
}
```

https://programmers.co.kr/learn/courses/30/lessons/60060
채점 결과
정확성: 25.0
효율성: 30.0
합계: 55.0 / 100.0

```
function solution(words, queries) {
    var answer = [];

    const regQueries = queries.map((querie) => {
        return RegExp(querie.replace(/\?/g, '.'))
    })

    let mapWordLength = {}

    let word = ''
    for(let j = 0 ; j < words.length ; j += 1) {
        word = words[j]

        if (mapWordLength[word.length] === undefined) {
            mapWordLength[word.length] = []
        }

        mapWordLength[word.length].push(word)
    }

    let regQuerie
    let wordLength
    for (let i = 0 ; i < queries.length ; i += 1) {
        answer[i] = 0;
        regQuerie = regQueries[i];

        wordLength = mapWordLength[queries[i].length] || []

        for(let j = 0 ; j < wordLength.length ; j += 1) {
            if (regQuerie.test(wordLength[j])) {
                answer[i] += 1;
            }
        }
    }

    return answer;
}
```
