# DigitalString class

## usage

run ./dstring

## intro

��ʼ����string��ͬ.

### string sprint(const string& str, int pos) const;

str֧��ʶ��"%d","%f","%lf"����,�ɼ���".(number)","-(number)"�Ȳ���

pos��ʾ��dstring���Ϊpos���ַ�(��0��ʼ)��Ϊ��һ���ַ�.

������:

"%(number)d" ȡnumber���ַ�,δȡ��ʱ��ǰ�油���ɿո񲹵�number,ȱʡʱĬ��ȡ��ĩβ.

"%.(number)d" ͬ��,δȡ��ʱ��ǰ�油����0����number,����ȱʡ.

"%(num1).(num2)d" ȡnum2���ַ�,���㲹0,num1>num2ʱ�Ҷ���

"%-(num1).(num2)d" ͬ��,num1>num2ʱ�����

��ʵ��:

"%(num1).(num2)lf" ȡnum1���ַ�,������С�����num2λ,num1ȱʡʱĬ��ȡ��dstringĩβ,num2ȱʡʱĬ��6λ.

���main.cpp.

### int is(int pos) const;

����dstring���posλ������.
