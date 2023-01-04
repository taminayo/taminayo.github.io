```cpp
int concat(const vector<int>& lengths) {
	priority_queue<int, vector<int>, greater<int>> pq;
	for (int i = 0; i < lengths.size(); ++i) {
		pq.push(lengths[i]);
	}
	int res = 0;

	while (pq.size() > 1) {
		int min1 = pq.top(); pq.pop();
		int min2 = pq.top(); pq.pop();
		pq.push(min1 + min2);
		res += min1 + min2;
	}
	return res;
}
```

Subploblem result affects to next step. So, we need to import _pririty_queue_.
