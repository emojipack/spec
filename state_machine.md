# State Machine Proposal

Finite state machine specification for client send and receive. Should be equivalent to what we've discussed today.

## On message receive

```flow
st=>start: Message recieved
e1=>end: End
e2=>end: Upload and send resource
e3=>end: End

cond1=>condition: Has header?
cond2=>condition: Is pack request?
parse=>subroutine: Parse header
haspack=>condition: Is missing emoji?
msg1=>subroutine: Send request and await response

st->cond1
cond1(yes@yes)->parse->cond2
cond1(no@no)->e1
cond2(yes@yes,right)->e2
cond2(no@message must be an emojipack list)->haspack
haspack(yes@yes)->msg1(left)->haspack
haspack(no@no/response timeout)->e3

```

## On text message send

```flow
st=>start: Pending message send
e=>end: Send

sync=>condition: Need to sync?
gen=>subroutine: Generate header

st->sync
sync(yes@yes)->gen->e
sync(no@no)->e
```
