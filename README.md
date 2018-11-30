package com.exam.myapplication;

import android.content.Intent;
import android.os.Bundle;
import android.support.design.widget.FloatingActionButton;
import android.support.design.widget.Snackbar;
import android.view.View;
import android.support.design.widget.NavigationView;
import android.support.v4.view.GravityCompat;
import android.support.v4.widget.DrawerLayout;
import android.support.v7.app.ActionBarDrawerToggle;
import android.support.v7.app.AppCompatActivity;
import android.support.v7.widget.Toolbar;
import android.view.Menu;
import android.view.MenuItem;

import com.exam.myapplication.Fragmant.Fragment1;
import com.exam.myapplication.Fragmant.Fragment2;
import com.exam.myapplication.Fragmant.Fragment3;
import com.exam.myapplication.Fragmant.Fragment4;
import com.exam.myapplication.Fragmant.Fragment5;

import morningandevenings2019.imagesw.com.myapplication.R;

public class MainActivity extends AppCompatActivity
        implements NavigationView.OnNavigationItemSelectedListener {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Toolbar toolbar = (Toolbar) findViewById(R.id.toolbar);
     //   setSupportActionBar(toolbar);

        FloatingActionButton fab = (FloatingActionButton) findViewById(R.id.fab);
        fab.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
             //   Intent intent1 = new Intent(MainActivity.this, AddTascks.class);
            //    startActivity(intent1);
            }
        });

        DrawerLayout drawer = (DrawerLayout) findViewById(R.id.drawer_layout);
        ActionBarDrawerToggle toggle = new ActionBarDrawerToggle(
                this, drawer, toolbar, R.string.navigation_drawer_open, R.string.navigation_drawer_close);
        drawer.addDrawerListener(toggle);
        toggle.syncState();

        NavigationView navigationView = (NavigationView) findViewById(R.id.nav_view);
        navigationView.setNavigationItemSelectedListener(this);
    }

    @Override
    public void onBackPressed() {
        DrawerLayout drawer = (DrawerLayout) findViewById(R.id.drawer_layout);
        if (drawer.isDrawerOpen(GravityCompat.START)) {
            drawer.closeDrawer(GravityCompat.START);
        } else {
            super.onBackPressed();
        }
    }

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items to the action bar if it is present.
        getMenuInflater().inflate(R.menu.main, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle action bar item clicks here. The action bar will
        // automatically handle clicks on the Home/Up button, so long
        // as you specify a parent activity in AndroidManifest.xml.
        int id = item.getItemId();

        //noinspection SimplifiableIfStatement
        if (id == R.id.action_settings) {
            return true;
        }

        return super.onOptionsItemSelected(item);
    }

    @SuppressWarnings("StatementWithEmptyBody")
    @Override
    public boolean onNavigationItemSelected(MenuItem item) {
        // Handle navigation view item clicks here.
        int id = item.getItemId();

        if (id == R.id.fragmant1) {
            Fragment1 blankFragment=new Fragment1();
            getSupportFragmentManager().beginTransaction().replace(R.id.mincontain,blankFragment).commit();
//            Intent intent = new Intent(getApplicationContext(),Fragment1.class);
//            startActivity(intent);
        } else if (id == R.id.fragmant2) {
            Fragment2 blankFragment=new Fragment2();
            getSupportFragmentManager().beginTransaction().replace(R.id.mincontain,blankFragment).commit();
//            Intent intent = new Intent(getApplicationContext(),Fragment1.class);
//            startActivity(intent);

        } else if (id == R.id.fragmant3) {
            Fragment3 blankFragment=new Fragment3();
            getSupportFragmentManager().beginTransaction().replace(R.id.mincontain,blankFragment).commit();
//            Intent intent = new Intent(getApplicationContext(),Fragment1.class);
//            startActivity(intent);
        } else if (id == R.id.fragmant4) {
            Fragment4 blankFragment=new Fragment4();
            getSupportFragmentManager().beginTransaction().replace(R.id.mincontain,blankFragment).commit();
//            Intent intent = new Intent(getApplicationContext(),Fragment1.class);
//            startActivity(intent);

        } else if (id == R.id.fragmant5) {
            Fragment5 blankFragment=new Fragment5();
            getSupportFragmentManager().beginTransaction().replace(R.id.mincontain,blankFragment).commit();
//            Intent intent = new Intent(getApplicationContext(),Fragment1.class);
//            startActivity(intent);
        } else if (id == R.id.fragmant6) {
            Fragment6 blankFragment=new Fragment6();
            getSupportFragmentManager().beginTransaction().replace(R.id.mincontain,blankFragment).commit();
//            Intent intent = new Intent(getApplicationContext(),Fragment1.class);
//            startActivity(intent);
//        } else if (id == R.id.fragmant5) {
//            Fragment5 blankFragment=new Fragment5();
//            getSupportFragmentManager().beginTransaction().replace(R.id.mincontain,blankFragment).commit();
////            Intent intent = new Intent(getApplicationContext(),Fragment1.class);
////            startActivity(intent);
        } else if (id == R.id.nav_share) {

        } else if (id == R.id.nav_send) {

        }

        DrawerLayout drawer = (DrawerLayout) findViewById(R.id.drawer_layout);
        drawer.closeDrawer(GravityCompat.START);
        return true;
    }
}
