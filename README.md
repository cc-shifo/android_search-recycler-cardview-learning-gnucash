# search-recycler-cardview-learning-gnucash
####
`Demonstration`<br>
![](https://github.com/cc-shifo/search-recycler-cardview-learning-gnucash/raw/master/screenshot1.png)<br>

五、gnuCash 学习search菜单，cardView型的recyclerView。点击星号，三个冒号事件。
  AccountsActiviy.java是启动活动。对应的activity_accounts.xml是界面文件。
  FormAcitivity.java是点击浮动按钮后出现的界面。

  AccountsActiviy.java的行254
  // 设置viewpager适配器，适配器里有获取数据，设置item等。适配器在152行定义的。默认3个页
  // 对应“最近的”，“所有的”，“收藏”
  mPagerAdapter = new AccountViewPagerAdapter(getSupportFragmentManager());
  mViewPager.setAdapter(mPagerAdapter);
  
  // 设置ViewPager的页数，由AccountViewPagerAdapter.getCount返回。固定为3。
  // viewpager跟adapter以及数据的关系得知，adapter里有3个数据
  private static final int DEFAULT_NUM_PAGES = 3;
  
  // AccountActivity.java的279行
  // 点击浮动按钮“+”加号
  mFloatingActionButton.setOnClickListener(new View.OnClickListener() 
  // FormActivity.java就是点击“+”加号后启动的活动。

  // FormActivity.java活动的标题栏的“保存”按钮的xml文件default_save_actions.xml
  showAccountFormFragment()
  AccountFormFragment.newInstance()

  // FormActivity.java第123行
  // 创建科目界面从是点击浮动按钮进入的。“保存”按钮就是在这个标题栏上。
  // 只不过，保存按钮是在AccountFormFragment中初始化的。
  // FormActivity类与AccountFormFragment类是通过showAccountFormFragment关联的。
    @Override
    public boolean onOptionsItemSelected(MenuItem item)

  // 
  // 保存按钮 等菜单栏控件的View在AccountFormFragment类的这个函数中填充的。
  // 第560行，saveAccount()这个函数保存了刚才的数据。
    @Override
    public void onCreateOptionsMenu(Menu menu, MenuInflater inflater) 
  
  // AccountsListFragment类定义了一个RecyclerView，这个类的视图文件
  // fragment_accounts_list.xml

  // AccountActivity.java的getItem()会调用
  currentFragment = AccountsListFragment.newInstance(
                 AccountsListFragment.DisplayMode.RECENT);
  // 间接的创建了一个AccountsListFragment对象。也就创建了一个RecyclerView
  // "没有可以显示的科目，最近的科目为空，没有加星标的科目"也是在
  // AccountsListFragment这个类中创建的。

  // AccountActivity.java第381
  // 搜索内容改变后调用这个函数
  onQueryTextChange()

  // AccountActivity.java第275
  // 设置搜索框android.support.v7.widget.SearchView mSearchView
  onCreateOptionsMenu(Menu menu, MenuInflater inflater)
