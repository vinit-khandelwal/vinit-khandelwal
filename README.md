<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>LeetCode Problem Lists</title>

  <style>
    body {
      margin: 0;
      padding: 24px;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background: #f5f6fa;
    }

    h1 {
      text-align: center;
      margin-bottom: 32px;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
      gap: 20px;
    }

    .card {
      background: #ffffff;
      border-radius: 12px;
      overflow: hidden;
      text-decoration: none;
      color: #222;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .card:hover {
      transform: translateY(-4px);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.12);
    }

    .card img {
      width: 100%;
      height: 140px;
      object-fit: contain;
      background: #fafafa;
      padding: 12px;
    }

    .card-title {
      padding: 12px;
      text-align: center;
      font-size: 14px;
      font-weight: 600;
    }
  </style>
</head>

<body>
  <h1>LeetCode Curated Problem Lists</h1>

  <div id="grid" class="grid"></div>

  <script>
    const problemLists = [
      ["https://leetcode.com/problem-list/suffix-array/", "https://assets.leetcode.com/favorite/problemset/suffix-array.png", Suffix Array]
      ["https://leetcode.com/problem-list/monotonic-queue/", "https://assets.leetcode.com/favorite/problemset/monotonic-queue.png", Monotonic Queue]
      ["https://leetcode.com/problem-list/shell/", "https://assets.leetcode.com/favorite/problemset/shell.png", Shell]
      ["https://leetcode.com/problem-list/reservoir-sampling/" "https://leetcode.com/favorite/problemset/reservoir-sampling.png", Reservoir Sampling]
      ["https://leetcode.com/problem-list/radix-sort/", "https://assets.leetcode.com/favorite/problemset/radix-sort.png", Radix Sort]
      ["https://leetcode.com/problem-list/geometry/", "https://assets.leetcode.com/favorite/problemset/geometry.png", Geometry]
      ["https://leetcode.com/problem-list/interactive/", "https://assets.leetcode.com/favorite/problemset/interactive.png", Interactive]
      ["https://leetcode.com/problem-list/bucket-sort/", "https://assets.leetcode.com/favorite/problemset/bucket-sort.png", Bucket Sort]
      ["https://leetcode.com/problem-list/binary-indexed-tree/" "https://leetcode.com/favorite/problemset/binary-indexed-tree.png", Binary Indexed Tree]
      ["https://leetcode.com/problem-list/rolling-hash/", "https://assets.leetcode.com/favorite/problemset/rolling-hash.png", Rolling Hash]
      ["https://leetcode.com/problem-list/iterator/", "https://assets.leetcode.com/favorite/problemset/iterator.png", Iterator]
      ["https://leetcode.com/problem-list/data-stream/", "https://assets.leetcode.com/favorite/problemset/data-stream.png", Data Stream]
      ["https://leetcode.com/problem-list/simulation/", "https://assets.leetcode.com/favorite/problemset/simulation.png", Simulation]
      ["https://leetcode.com/problem-list/bitmask/", "https://assets.leetcode.com/favorite/problemset/bitmask.png", Bitmask]
      ["https://leetcode.com/problem-list/probability-and-statistics/", "https://assets.leetcode.com/favorite/problemset/probability-and-statistics.png", Probability and Statistics]
      ["https://leetcode.com/problem-list/counting-sort/", "https://assets.leetcode.com/favorite/problemset/counting-sort.png", Counting Sort]
      ["https://leetcode.com/problem-list/game-theory/", "https://assets.leetcode.com/favorite/problemset/game-theory.png", Game Theory]
      ["https://leetcode.com/problem-list/ordered-set/", "https://assets.leetcode.com/favorite/problemset/ordered-set.png", Ordered Set]
      ["https://leetcode.com/problem-list/enumeration/", "https://assets.leetcode.com/favorite/problemset/enumeration.png", Enumeration]
      ["https://leetcode.com/problem-list/randomized/", "https://assets.leetcode.com/favorite/problemset/randomized.png", Randomized]
      ["https://leetcode.com/problem-list/shortest-path/", "https://assets.leetcode.com/favorite/problemset/shortest-path.png", Shortest Path]
      ["https://leetcode.com/problem-list/monotonic-stack/", "https://assets.leetcode.com/favorite/problemset/monotonic-stack.png", Monotonic Stack]
      ["https://leetcode.com/problem-list/merge-sort/", "https://assets.leetcode.com/favorite/problemset/merge-sort.png", Merge Sort]
      ["https://leetcode.com/problem-list/depth-first-search/" "https://leetcode.com/favorite/problemset/depth-first-search.png", Depth-First Search]
      ["https://leetcode.com/problem-list/breadth-first-search/" "https://leetcode.com/favorite/problemset/breadth-first-search.png", Breadth-First Search]
      ["https://leetcode.com/problem-list/doubly-linked-list/" "https://leetcode.com/favorite/problemset/doubly-linked-list.png", Doubly-Linked List]
      ["https://leetcode.com/problem-list/segment-tree/", "https://assets.leetcode.com/favorite/problemset/segment-tree.png", Segment Tree]
      ["https://leetcode.com/problem-list/topological-sort/", "https://assets.leetcode.com/favorite/problemset/topological-sort.png", Topological Sort]
      ["https://leetcode.com/problem-list/counting/", "https://assets.leetcode.com/favorite/problemset/counting.png", Counting]
      ["https://leetcode.com/problem-list/minimum-spanning-tree/" "https://leetcode.com/favorite/problemset/minimum-spanning-tree.png", Minimum Spanning Tree]
      ["https://leetcode.com/problem-list/divide-and-conquer/" "https://leetcode.com/favorite/problemset/divide-and-conquer.png", Divide and Conquer]
      ["https://leetcode.com/problem-list/number-theory/", "https://assets.leetcode.com/favorite/problemset/number-theory.png", Number Theory]
      ["https://leetcode.com/problem-list/combinatorics/", "https://assets.leetcode.com/favorite/problemset/combinatorics.png", Combinatorics]
      ["https://leetcode.com/problem-list/union-find/", "https://assets.leetcode.com/favorite/problemset/union-find.png", Union Find]
      ["https://leetcode.com/problem-list/binary-search-tree/" "https://leetcode.com/favorite/problemset/binary-search-tree.png", Binary Search Tree]
      ["https://leetcode.com/problem-list/string-matching/", "https://assets.leetcode.com/favorite/problemset/string-matching.png", String Matching]
      ["https://leetcode.com/problem-list/tree/", "https://assets.leetcode.com/favorite/problemset/tree.png", Tree]
      ["https://leetcode.com/problem-list/trie/", "https://assets.leetcode.com/favorite/problemset/trie.png", Trie]
      ["https://leetcode.com/problem-list/greedy/", "https://assets.leetcode.com/favorite/problemset/greedy.png", Greedy]
      ["https://leetcode.com/problem-list/binary-tree/", "https://assets.leetcode.com/favorite/problemset/binary-tree.png", Binary Tree]
      ["https://leetcode.com/problem-list/recursion/", "https://assets.leetcode.com/favorite/problemset/recursion.png", Recursion]
      ["https://leetcode.com/problem-list/heap-priority-queue/" "https://leetcode.com/favorite/problemset/heap-priority-queue.png",   Heap (Priority Queue)]
      ["https://leetcode.com/problem-list/sorting/" bl"https://assets.leetcode.com/favorite/problemset/sorting.png", Sorting]
      ["https://leetcode.com/problem-list/hash-table/", "https://assets.leetcode.com/favorite/problemset/hash-table.png", Hash Table]
      ["https://leetcode.com/problem-list/concurrency/", "https://assets.leetcode.com/favorite/problemset/concurrency.png", Concurrency]
      ["https://leetcode.com/problem-list/backtracking/", "https://assets.leetcode.com/favorite/problemset/backtracking.png", Backtracking]
      ["https://leetcode.com/problem-list/database/", "https://assets.leetcode.com/favorite/problemset/database.png", Database]
      ["https://leetcode.com/problem-list/two-pointers/", "https://assets.leetcode.com/favorite/problemset/two-pointers.png", Two Pointers]
      ["https://leetcode.com/problem-list/sliding-window/", "https://assets.leetcode.com/favorite/problemset/sliding-window.png", Sliding Window]
      ["https://leetcode.com/problem-list/bit-manipulation/", "https://assets.leetcode.com/favorite/problemset/bit-manipulation.png", Bit Manipulation]
      ["https://leetcode.com/problem-list/prefix-sum/", "https://assets.leetcode.com/favorite/problemset/prefix-sum.png", Prefix Sum]
      ["https://leetcode.com/problem-list/matrix/", "https://assets.leetcode.com/favorite/problemset/matrix.png", Matrix]
      ["https://leetcode.com/problem-list/design/", "https://assets.leetcode.com/favorite/problemset/design.png", Design]
      ["https://leetcode.com/problem-list/linked-list/", "https://assets.leetcode.com/favorite/problemset/linked-list.png", Linked List]
      ["https://leetcode.com/problem-list/math/", "https://assets.leetcode.com/favorite/problemset/math.png", Math]
      ["https://leetcode.com/problem-list/stack/", "https://assets.leetcode.com/favorite/problemset/stack.png", Stack]
      ["https://leetcode.com/problem-list/queue/", "https://assets.leetcode.com/favorite/problemset/queue.png", Queue]
      ["https://leetcode.com/problem-list/string/", "https://assets.leetcode.com/favorite/problemset/string.png", String]
      ["https://leetcode.com/problem-list/array/", "https://assets.leetcode.com/favorite/problemset/array.png", Array]
      ["https://leetcode.com/problem-list/binary-search/", "https://assets.leetcode.com/favorite/problemset/binary-search.png", Binary Search]
      ["https://leetcode.com/problem-list/dynamic-programming/" "https://leetcode.com/favorite/problemset/dynamic-programming.png", Dynamic Programming]
      ["https://leetcode.com/problem-list/graph/", "https://assets.leetcode.com/favorite/problemset/graph.png", Graph]
    ];

    const grid = document.getElementById("grid");

    problemLists.forEach(([link, image, title]) => {
      const card = document.createElement("a");
      card.className = "card";
      card.href = link;
      card.target = "_blank";

      card.innerHTML = `
        <img src="${image}" alt="${title}">
        <div class="card-title">${title}</div>
      `;

      grid.appendChild(card);
    });
  </script>
</body>
</html>
