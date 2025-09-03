assets khác với public:
- Gắn trực tiếp vào code/component → src/assets/.

VD:
//1
import Logo from "@/assets/logo.svg"
<img src={Logo} />

//2
.hero {
  background-image: url("@/assets/hero-bg.jpg");
}

//3

src/assets/fonts/Inter.woff2

@font-face {
  font-family: "Inter";
  src: url("@/assets/fonts/Inter.woff2") format("woff2");
}


- Phục vụ tĩnh, URL cố định → public/.

VD:

//1
public/favicon.ico

//2
public/robots.txt
public/manifest.json

//3
Ảnh, video lớn ít thay đổi:
public/videos/intro.mp4

<video src="/videos/intro.mp4" controls >

