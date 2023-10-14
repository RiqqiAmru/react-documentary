# react-documentary
repo ini berisi pembelajaran saya pribadi men *translate* dokumentasi [react](https://react.dev) , sekaligus belajar lebih dalam mengenai *markdown*, dan bahasa inggris

## REACT
library untuk web dan native user interfaces
[Learn React](learn.md), [API References](api-references.md)

## Membangun User Interfaces dari beberapa Component
React memungkinkanmu membangun user interfaces dari beberapa bagian yang disebut components. Buat sendiri React Component mu seperti Thumbnails, LikeButton, & Video. Kemudian dikombinasikan menjadi seluruh layar, halaman, dan aplikasi. 

``` jsx
function Video({video}){
    return(
        <div>
          <Thumbnail video={video}/>
          <a href={video.url}>
           <h3>{video.url}</h3>
           <p>{video.description}</p>
          </a>
        </div>
    )
}
```

Tidak peduli apakah kamu bekerja sendiri ataupun dengan ribuan developer lain, menggunakan react terasa sama. React di desain untuk memudahkanmu mengkombinasikan Component yang di tulis oleh berbagain orang, tim, ataupun organisasi. 

## Tulis Components dengan code dan markup
React Component adalah JavaScript Functions. Ingin melihat konten dengan logika kondisional?. Gunakan **if** statement. Menampilkan list?. Coba array **map()**. Belajar React sama seperti belajar programming. 

```jsx
import { useState } from 'react';

function SearchableVideoList({ videos }){
    const [searchText, setSearchText] = useState('');
    const foundVideos = filterVideos(videos, searchText);
    return(
        <>
            <SearchInput 
                value={searchText} 
                onChange={newText => setSearchText(newText)}/>
            <VideoList 
             videos={foundVideos}
             emptyHeading={`No matches for "${searchText}"`}
            />
        </>
    )
}
```
Kamu tidak diharuskan membangun seluruh halaman dengan React. Tambahkan React ke halaman HTML mu, dan render interactive React Components dimana saja di dalamnya.  
[Add React to Your Page](learn##add-react-to-your-page)

## Jadilah full-stack dengan framework
React adalah library. yang memungkinkanmu meletakkan components bersamaan, meskipun react sendiri tidak menentukan bagaimana cara routing dan fetch data. untuk membangun aplikasi dengan React, kami menyarankan  full-stack react framework seperti (Next.js)[https://nextjs.org] atau (Remix)[https://remix.run]
``` js
import {db} from './database.js';
import {Suspense} from 'react';

async function ConferencePage({slug}){
    const conf = await db.Confs.find({slug});
    return(
        <ConferenceLayout conf={conf}>
         <Suspense fallback={<TalksLoading />}>
          <Talks confId={conf.id}/>
         </Suspense>
        </ConferenceLayout>
    )
}

async function Talks({confId}){
    const talks = await db.Talks.findAll({confId});
    const videos = talks.map((talk)=>{talk.video});
    return <SearchableVideoLilst videos={videos}>
}
```

React juga merupakan arsitektur. Framework yang mengimplementasikannya memungkinkanmu mengambil data (*fetch*) dari component asynchronous yang berjalan di server atau ketika build. Membaca data dari file atau database, dan menyalurkan/mengirimkannya ke interaktif components.
(Get Started with a framework)[]

## Gunakan yang terbaik dari setiap platform
Orang-orang menyukai web dan aplikasi native untuk beberapa alasan. React memungkinkanmu membangun kedua aplikasi (web dan native) menggunakan skill yang sama. *condong* ke masing-masing kekuatan unik platform yang menjadikan interfaces mu terasa tepat di setiap platform.

### Tetap benar di web
Orang-orang mengharap aplikasi web untuk cepat di muat. Ketika di server, react memungkinkanmu mengalirkan *(streaming)* HTML ketika masih fetch data, secara progressive mengisi konten saat ini bahkan sebelum kode JavaScript di muat. di Browser klien, React bisa menggunakan standar Web API untuk menjaga UI mu responsive bahkan ketika ditengah-tengah rendering. 

### Benar Benar Native
Orang mengharap aplikasi native terlihat dan terasa seperti platform mereke. (React Native)[https://reactnative.dev] dan (Expo)[https://github.com/expo/expo] memungkinkanmu membangun aplikasi React di android, iOS, dan lainnya. Mereka terlihat dan terasa seperti native karena UI nya benar-benar native, bukan web view. React componentmu merender tampilan asli Android dan iOS sesuai dengan masing-masing platform. 

Dengan react, kamu bisa menjadi developer web dan native. Tim mu bisa membangun berbagai platform tanpa mengorbankan user experience. Organisasi bisa *menjembatani platform silo*, dan membentuk tim yang memiliki seluruh fitur end-to-end
(Build for Native platforms)[https://reactnative.dev]

## Upgrade ketika masa depan siap
React mengadopsi perubahan dengan hati-hati. Setiap commit react di test pada *business-critical* oleh jutaan user. lebih dari 100.000 react component di Meta membantu memvalidasi setiap strategi perubahan (*migration*)

React Tim selalu melakukan research untuk memajukan React. beberapa penelitian membutuhkan waktu bertahun-tahun. react memiliki antrian tinggi untuk meletakkan ide penelitian ke tahap production. hanya yang terbuktilah yang menjadi bagian dari react. 

## Bergabung ke jutaan komunitas
Kamu tidak sendiri, 2 juta developer dari seluruh duna mengunjungi dokumentasi React setiap bulannya. React memiliki sesuatu yang membuat orang-orang dan tim bersatu. 

Inilah kenapa React lebih dari *library*, arsitektur, ataupun ekosistem. React adalah komunitas. adalah temmpat dimana kamu bisa meminta bantuan, mencari kesempatan, dan bertemu teman baru. kamu akan menemukan banyak developer, desainer, pemula, ahli, peneliti dan artist, guru dan murid. latar belakang kami mungkin berbeda-beda, namun React membiarkan kita semua membuat user interface bersama. 

(Get Started)[learn.md]
