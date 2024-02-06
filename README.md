
# How to make a RecyelerView


## Authors

- [@SiamShekh](https://www.github.com/SiamShekh)


## XML

design as you want

```bash
  <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/recyclerview"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"/>
```
    
    
## Java

Make RecyclerView Adapter

```bash
  protected class Adapter extends RecyclerView.Adapter{}
```

Make RecyclerView ViewHolder

```bash
  protected class ViewHolder extends RecyclerView.ViewHolder{}
```

Make getItemViewType

```bash
   @Override
        public int getItemViewType(int position) {
            hashMap = arrayList.get(position);
            String TYPE = hashMap.get("TYPE");
            if (TYPE.equals("1")) {
                return 1;
            } else if (TYPE.equals("2")) {
                return 2;
            } else if (TYPE.equals("3")) {
                return 3;
            } else {
                return super.getItemViewType(position);
            }
        }
```

Make RecyclerView onCreateViewHolder

```bash
   @NonNull
        @Override
        public RecyclerView.ViewHolder onCreateViewHolder(@NonNull ViewGroup viewGroup, int i) {
            LayoutInflater layoutInflater = getLayoutInflater();
            if (i == 1) {
                View view = layoutInflater.inflate(R.layout.item_1, viewGroup, false);
                return new FirstModel(view);
            } else if (i == 2) {
                View view = layoutInflater.inflate(R.layout.item_2, viewGroup, false);
                return new SecModel(view);
            } else if (i == 3) {
                View view = layoutInflater.inflate(R.layout.item_3, viewGroup, false);
                Toast.makeText(Recycler_View.this, "1", Toast.LENGTH_SHORT).show();

                return new ThModel(view);
            }else {
                View viewParent = layoutInflater.inflate(R.layout.item_1, viewGroup, false);
                return new FirstModel(viewParent);
            }
        }
```

Make RecyclerView onBindViewHolder

```bash
  @Override
        public void onBindViewHolder(@NonNull RecyclerView.ViewHolder viewHolder, int i) {
            if (getItemViewType(i) == 2){
                Toast.makeText(Recycler_View.this, "1", Toast.LENGTH_SHORT).show();
            }
        }
```
