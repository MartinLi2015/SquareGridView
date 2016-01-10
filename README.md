# SquareGridView

SquareGridView is a viewGroup for display multiple images, it is more light than GridView and GridLayout!
I has optimize the reuse performance in recyclerView and ListView for you! Now listview can scroll super smooth
when you add severial images into each cell.

Please feel free to use! Any questions you can add a issue or email me aliouswang@gmail.com!

# Download     

```
Gradle:

compile 'com.aliouswang:library:1.0.0'

```

# How do I use SquareGridView

1. Add SquareGridView into you layout xml file.
```
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal"
    >
    <RelativeLayout
        android:layout_width="match_parent"
        android:background="@android:color/holo_blue_dark"
        android:layout_weight="1"
        android:layout_height="wrap_content">

        <com.aliouswang.view.library.SquareGridView
            android:id="@+id/square_grid_view"
            app:numColumns="3"
            app:maxSize="9"
            app:verticalSpacing="5dp"
            app:horizontalSpacing="5dp"
            app:ratio="0.8"
            android:padding="5dp"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"/>

    </RelativeLayout>
  </LinearLayout>
  ```
2. Attach dataSource to SuqareGridView.
```
SquareGridView squareGridView = (SquareGridView) convertView
                    .findViewById(R.id.square_grid_view);
            final Diary diary = mDiaryList.get(position);
            SquareViewAdapter<Diary> adapter = new SquareViewAdapter<Diary>() {
                @Override
                public int getCount() {
                    return diary.photos.size();
                }

                @Override
                public Diary getItem(int position) {
                    return diary;
                }

                @Override
                public String getImageUrl(int position) {
                    return diary.photos.get(position);
                }

                @Override
                public void onItemClick(View view, int index, Diary t) {
                    Toast.makeText(MainActivity.this,
                            "index :" + index, Toast.LENGTH_SHORT).show();
                }
            };
squareGridView.setAdapter(adapter);
```

# Licence
  Apache 2.0
  
# Author
  aliouswang
  aliouswang@gmail.com
