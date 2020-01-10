# ⭐ Enum

```java
    public enum Type {
    
        READ, LIKED, LATER;
    
        private int id;
    
        static {
            READ.id = 1;
            LIKED.id = 2;
            LATER.id = 3;
        }
    
        public int getId() {
            return this.id;
        }
    
        public State findState(List<State> stateList) {
            for (State state : stateList) {
                if (state.getType() == this.getId()) {
                    return state;
                }
            }
            return null;
        }
    
        public boolean isExist(List<State> stateList) {
            return findState(stateList) != null;
        }
    
        @NonNull
        @Override
        public String toString() {
            return String.valueOf(this.getId());
        }
    }

...

Type.LATER.getId()
Type.LATER.findState(.)
msg = "" + Type.LATER // To string
    
```

