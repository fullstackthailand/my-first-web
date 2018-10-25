# update
  ##### Laravel 5.6 Training Course.pdf
  ##### LARAVEL วันที่ 3.pdf

# Contact Point
  ## Surawut Sodasak (GET )
    ### Email : surawut.sod@gmail.com
    ### Facebook : https://www.facebook.com/surawut.sodasak

# Dropdown From Database (Done)
  - Adding Migration => database/migrations/2018_07_10_104651_create_cities_table.php
  - Adding Seeder => database/seeds/CityTableSeeder.php
  - Adding Model => app/Model/City.php
  - Editing Controller Method create, edit => app/Http/Admin/UsersController.php
  - Editing View => resources/views/user/create.blade.php Line : 104 - 108
  - Editing View => resources/views/user/edit.blade.php Line : 104 - 108

# training-laravel56 Document links
https://docs.google.com/document/d/1qNxHzG1hEnUkU9ORk8GiBDlRrSg9ZN6tcWCkw2mz6ZY/edit#heading=h.tcpw8tqvvnfp
https://github.com/thenesta/laravel56-training

# Json Sample APIs
https://api.github.com/users/hadley/orgs

# Bootstrap
https://startbootstrap.com/template-categories/admin-dashboard/
https://getbootstrap.com/docs/4.0/components/modal/

# Example & Tutorial form P' Peck
https://github.com/thenesta/laravel56-training

# Google Document Links form P' Peck
https://docs.google.com/document/d/1ef0xdw_XW2KhpqLdrNsXkmEGZ4syaGK06_8IIHqdXGc/edit?usp=sharing


## ตอนนี้ Code ที่สอน Version ที่สมบูรณ์ ได้ถูก Push ขึ้นมายัง git ตัวนี้แล้ว โดยสามารถกดจากปุ่ม หน้า Users List ได้เลย โดยมี URL ในแต่ละส่วน ดังนี้
Lists User (Method GET) : http://www.training.me/admin/user
Create User (Method GET) : http://www.training.me/admin/user/create    //แสดงหน้า Create New User Form HTML
Store User (Method POST) : http://www.training.me/admin/user    //Insert User ลง Table
    -- parameter พิเศษคือ
        _token คือค่า token csrf ที่สร้างจาก framework

Edit User (Method GET) : http://www.training.me/admin/user/create    //แสดงหน้า Edit User Form HTML
Update User (Method POST) : http://www.training.me/admin/user/{id}     //Insert User ลง Table
    -- parameter พิเศษคือ
        _method มีค่าคือ PUT ใช้สำหรับเป็น วิธีเพื่อให้ใช้ Method PUT ผ่าน POST Form ได้
        _token คือค่า token csrf ที่สร้างจาก framework

# สิ่งที่เพิ่มมาจากการสอน คือ
  - User Validation Service อยู่ที่ Controller User ใช้ UserRequest แทน Request ตอน Inject เข้า public function update(UserRequest $request, $id) และ use App\Http\Requests\UserRequest;
 โดยใช้การสร้าง UserRequest ด้วย php artisan make:request UserRequest

 - Custom Rule เพื่อใช้สร้าง Validation Rule ของตัวเองขึ้นมา โดยใช้ php artisan make:rule FiveCharacters และไฟล์จะถูกสร้างที่ app/Rules/FiveCharacters และถูกเรียกใช้ โดย App\Http\Requests\UserRequest ใน function

 private function getPutRules()
 {
     $rules = $this->rules;
     //Change for Update (PUT Method)
     //$rules['name']  =  'required|min:1';
     $rules['name'] =  ['required', new FiveCharacters($this->name)];

     return $rules;
 }

# Zip
 https://drive.google.com/file/d/1SwUhnOvfND2re76HPegTroIx3sBo5M2-/view?usp=sharing
