# htmlparser
## intro

this is a simple htmlparser

author: yyq

�ص�: ʹ����HtmlParser���Tag��,������XML��׼�����˱�ǩ��; ʹ����������ʽ(�ɼ�consts.h)

----- update: 5.10  12:53 -----

��������ȡ����( texts() )����.

	  
## environment

linux (tested in ubuntu 16.04)

## general usage

1.�ڵ�ǰĿ¼������make�õ���ִ���ļ�htmlparser

```
make
```

2.��htmlparser.in��������������(��������ʡ��):

[html] ���ش������ļ�(html/php/...)

[dom] �������ļ���Ӧ����վurl(��http://www.baidu.com, http://info.ruc.edu.cn)

[mode] (default mode = 0)

	   mode = 0 : HtmlParser��ʹ��ifstream����
	   
	   mode = 1 : HtmlParser��ʹ��stringstream����
	   
	   ����ʵ�ַ����ɼ�main.cpp

3.����./htmlparser (����error: XXX����������)

```
./htmlparser
```

  ����̨��������ļ���title, ��ȡlink, text, image, sound, word������, ����link ��ʾurl����, text��ʾ����, image��ʾͼƬ, sound��ʾ��Ƶ, word��ʾ���ೣ���ļ�(word,pdf...),

  ���ڵ�ǰĿ¼�½���������ļ���:link, text, image, sound, word,�ֱ�洢���������ļ�.

## how to test

   ���������ȡ�����ṩ������ʵ������ȡ���Ӻ�������ÿһ��ʵ����������֤����

   1.����image:
   
     ��htmlparser.in����

		academic_faculty.php http://info.ruc.edu.cn

   2.����sound:

	 ��htmlparser.in����

		sope.html http://sope.ruc.edu.cn

   3.����word:

	 ��htmlparser.in����

		codeforces.html http://codeforces.com

## optional usage

(���htmlparser.h)

### HtmlParser���ṩ�Ľӿ�

    Tag* root();

    ���ظ���ǩ��ָ��,û�з���NULL
   
    std::string title() const;

    ���ر���
   
    Tag head() const;

    ����<head>��ǩ,û�з���nul_tag (const)
   
    Tag body() const;

    ����<body>��ǩ,û�з���nul_tag
	
    int links(std::string path = def_path, const std::string& file = def_linkfile);

    ��ȡ��ǰ�ļ��������Ӳ�����һ���ļ���, path ��ʾ�洢Ŀ¼, file��ʾ�洢���ĸ��ļ�, Ĭ��path = "", file = "links.txt"

	int texts(std::string path = def_path, const std::string& file = def_textfile);

	��ȡ��ǰ�ļ��������Ĳ�����һ���ļ���, path ��ʾ�洢Ŀ¼, file��ʾ�洢���ĸ��ļ�, Ĭ��path = "", file = "texts.txt"
   
    int images(const std::string& path = def_path);

    ��ȡ����ͼƬ, path ��ʾ�洢Ŀ¼
   
    int sounds(const std::string& path = def_path);

    ��ȡ������Ƶ�ļ�, path ��ʾ�洢Ŀ¼
   
    int words(const std::string& path = def_path);

    ��ȡ���а칫�ļ�, path ��ʾ�洢Ŀ¼

    Tag find(const std::string& str) const;

    ��������Ϊstr�ı�ǩ, ���ж�����ص�һ��, ���򷵻�nul_tag (const)
   
    std::vector<Tag> find_all(const std::string& str) const;

    ��������Ϊstr�ı�ǩ, ����һ���������б�ǩ��vector, ��û�з���һ����vector

### Tag���ṩ�Ľӿ�

    std::string name;

    ���ر�ǩ��
   
    std::vector<std::string> strs, cmts;

    ��ǩ������(strs)��ע��(cmts)
	
    std::map<std::string, std::string> attrs;

    ��ǩ�����Ե�map
   
    const std::string& operator [](const std::string& str) const;

    ���ص�ǰ��ǩ������str��ֵ,���û��������Է���nul_str (const)
   
    int links(std::string path = def_path, const std::string& file = def_file);

    ��ȡ��ǰ��ǩ��(�����ӱ�ǩ)�������Ӳ�����һ���ļ���, path ��ʾ�洢Ŀ¼, file��ʾ�洢���ĸ��ļ�, Ĭ��path = "", file = "links.txt"

	int texts(std::string path = def_path, const std::string& file = def_textfile);

	��ȡ��ǰ��ǩ��(�����ӱ�ǩ)�������Ĳ�����һ���ļ���, path ��ʾ�洢Ŀ¼, file��ʾ�洢���ĸ��ļ�, Ĭ��path = "", file = "texts.txt"	
	
    int images(const std::string& path = def_path);

    ��ȡ��ǰ��ǩ��(�����ӱ�ǩ)����ͼƬ, path ��ʾ�洢Ŀ¼
   
    int sounds(const std::string& path = def_path);

    ��ȡ��ǰ��ǩ��(�����ӱ�ǩ)������Ƶ�ļ�, path ��ʾ�洢Ŀ¼
   
    int words(const std::string& path = def_path);

    ��ȡ��ǰ��ǩ��(�����ӱ�ǩ)���а칫�ļ�, path ��ʾ�洢Ŀ¼

    Tag find(const std::string& str) const;

    ���ҵ�ǰ��ǩ������Ϊstr�ı�ǩ, ���ж�����ص�һ��, ���򷵻�nul_tag (const)
   
    std::vector<Tag> find_all(const std::string& str) const;

    ���ҵ�ǰ��ǩ������Ϊstr�ı�ǩ, ����һ���������б�ǩ��vector, ��û�з���һ����vector

	Tag* prev() const;

	�����뵱ǰ��ǩƽ�е���һ����ǩ(��֮�й�ͬ���׵ı�ǩ),û�з���NULL
	
	Tag* next() const;

	�����뵱ǰ��ǩƽ�е���һ����ǩ(��֮�й�ͬ���׵ı�ǩ),û�з���NULL
	
	Tag* fa() const;

	���ظ��ױ�ǩ,û�з���NULL
	
	Tag* son() const;

	���ص�һ�����ӵı�ǩ,û�з���NULL
