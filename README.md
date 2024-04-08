# -ProgrammingLanguageExperiment
# C言語
## コンパイル、実行
1. 目的のファイルが存在するディレクトリに移動
2. cc -o <コンパイル後ファイル名> <目的のファイル名>
3. ./<コンパイル後ファイル名>

## 複数行読み込み
https://yu-nix.com/archives/c-fgets/
char buf[100];  
while (fgets(buf, sizeof buf, stdin) != NULL) {  
    printf("buf[%s]\n", buf);  
}  
// Ctrl + Dで終了

## ファイルを開いて1行ずつ読み込み
FILE *fin = fopen("<読み込み先ファイル名>", "r");  
if (fin == NULL) {  
    perror("fopen");  
    return 1;  
}  
char buf[100];  
while (fgets(buf, sizeof buf, fin) != NULL) {  
    printf("%s", buf);  
}  
fclose(fin);  