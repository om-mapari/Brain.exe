
1.  Next Greater Element to Right

step 1. -

step 2. a

setp 3. +

for(int i=n-1 ; i\>=n ; i--)

{

// We need next greater

// therefore pop stack untill top \< arr\[i\]

// then top will be your next greater

while(!st.empty() && arr\[st.top()\] \< arr\[i\]

st.pop();

ans = st.empty() ? -1 : arr\[st.top()\]

st.push(arr\[i\])

}
