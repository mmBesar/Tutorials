# Tesseract OCR

## About Tesseract OCR - تعريف بالأداة

[wikipedia](https://en.wikipedia.org/wiki/Tesseract_(software))  
[Github](https://github.com/tesseract-ocr/tesseract)  

## install - التنصيب

- Fedora

>pre-installed on Fedora 36

```sh
sudo dnf install tesseract
```

- Ubuntu

```sh
sudo apt install tesseract-ocr
```

- Arch

```sh
sudo pacman -Sy
sudo pacman -S tesseract-data-eng
```

## Arabic Support - دعم اللغة العربية

- Fedora

```sh
sudo dnf install tesseract-langpack-ara
```

- Ubuntu

```sh
sudo apt install tesseract-ocr-ara
```

- Arch

```sh
sudo pacman -S tesseract-data-ara
```

## Usage - الاستخدام

- Arabic only - اللغة العربية فقط

```sh
tesseract -l ara image.png text
```

- English only - اللغة الإنجليزية فقط

```sh
tesseract -l eng image.png text
```

- Arabic and English - العربية والإنجليزية معًا

```sh
tesseract -l ara+eng image.png text
```

> More Examples - مزيد من الأمثلة: [here - هنا](https://tesseract-ocr.github.io/tessdoc/Command-Line-Usage.html)