<!--
 * @Description: In User Settings Edit
 * @Author: your name
 * @Date: 2019-07-28 13:31:42
 * @LastEditTime: 2019-08-30 22:33:40
 * @LastEditors: Please set LastEditors
 -->
# ǰ��
�ڿ�ʼ�����Ļ���Nordic BLEоƬ��SIG Mesh����֮ǰ��������������˽�Nordic�ٷ��ṩ��SDK���Ŀ�ܣ�**��Ҫһ�����Ͳ������绢�����������Լ�250**

![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/crazy%20operation.png)

# �������Mesh SDK
Ŀǰ����Mesh SDK�������ķ�ʽ�����֣�
- [Nordic��������](https://www.nordicsemi.com/Software-and-Tools/Software/nRF5-SDK-for-Mesh/Download#infotabs)

  ���ַ�ʽ�Ƚϼ򵥣������Ҳ��Ƽ���ԭ������Ҫ�����Ϲٷ��鿴�Ƿ��и��¡�������֪��Nordic�����е�ʱ������ǿ���������Ƣ���Ĺ���ʦ����Ҫ������:laughing:��ˣ����ַ�ʽ�ҾͲ�ϸ˵�ˣ�
- Nordic�Ĺٷ�Github���������
  
  С���Ǳ����Ƴ����ַ�ʽ�ģ��������Git���ߵ����ƣ������������£�
  - ����
    ```c
    git clone https://github.com/NordicSemiconductor/nRF5-SDK-for-Mesh.git
    ```
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Mesh%20downloading.gif)
  - ����  
    ```c
    git pull
    ```
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_sdk_update.png)

# SDKһ��
�������������SDK֮�����������ǿ���Nordic_MESH SDK���ļ��������ô���ġ�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_sdk_contents.png)

- .git
  
  ������һЩgit��ص����ݣ�����ĵ����ݼ������ļ�¼��ֻҪ�Ǵ�Github���������Ķ���������ص��ļ��У�

- bin
  - blinky

    �����Nordic ��ͬоƬ��ͬ�汾Э��ջ��blinky���̵�Hex�ļ����û�ֻҪ�Ժ��������������Լ���ƽ̨�������ˣ�

  - bootloader
    - armcc
      
      ��Ų�ͬоƬ��ͬ�汾Э��ջ�Ĵ������Լ��������ڵ�bootloader Hex�ļ�������**armcc**����Keil ARMCC������
    - gccarmemb

      �������**armcc**��һ��������bootloader��Hex�ļ�,ֻ�ǹ�������ͬ���ѣ���**gccarmemb**����GNU ARM Embedded������
  - merged
  
    ����ļ��д����һЩ���̺ϲ���Hex�ļ�,��bootloader�Ͳ�ͬЭ��ջ�ĺϲ���Ӧ�ó���Ͳ�ͬЭ��ջ�ĺϲ��ļ����ǹٷ�Ԥ�ȱ��벢�ϲ��õ�Hex�ļ����û�����ֱ�����������Ӧ�����ͺźͿ����弴�ɹ�����
  - ospace

    ����ļ��и�������ļ�����һЩ�غϣ�Ҳ�ǰ���һЩ�ٷ�Ԥ�ȱ���õ����ʾ�����̵�Hex�ļ��Լ�һЩʹ�õ��ĵ������Ŀ��ļ���
  - softdevice

    ��Ų�ͬ�汾��Э��ջ��Hex�ļ������Դ���ǲ��ṫ���ľ�����Hex�ļ�����ʽ�ṩ��
- CMake
  
  CMake��ص�һЩ�ļ�������ʲô��CMake�����Բο���[����](https://www.baidu.com/link?url=1UTIpsiOR1qjnqbkcT8CaQdM4AjGodTgAc4xgaAwAye&wd=&eqid=9629f3c600040a3d000000065d44084b)���򵥵���˵��������������makefiles��Ȼ��ʹ�ñ��빤���������������յĹ̼���

- doc

  ���ļ��д�ŵ���Nordic�ٷ��ṩ��һЩ���ŵ�ѧϰ���£��硰ģ�͡��ĸ���������Mesh��Nordic Mesh�Ŀ�ܽ��ܵȵȣ�**ǿ�ҽ������˴�����ļ��п�ʼ���ǵ�Mesh֮��**��

- examples

  ���ļ��е����������ǿ��Ժ����������ļ��д�ŵľ��ǹٷ��ṩ�����ǵ�ʾ�����̣����ǿ��Բο���Щ���̿�ʼ���ǵ���Ŀ�������������ʾ����������ʲô�õģ����ǿ����Ķ����ļ����µ� **��README��**�����˽����ʾ�����̵Ĺ��ܡ�

- external

  �����ŵ���Nordicʹ�õ��ĵ������Ĺ���ģ���Դ�롣

- mesh

  ���ļ�����SDK����Ҫ����ɲ��֣������ŵ���Nordic Mesh��Դ�룬�����������Ժ��õ���Mesh��صĹ��ܶ���������ļ�����ʵ�ֵģ��������������˽⼴�ɣ�**ǿ�Ҳ�����ȥ�Ķ���ЩԴ�룡����**

- models

  ����˼�壬�ô���ŵ���ĿǰΪֹNordic�ٷ��Ѿ�ʵ�ֵ�Model������SIG Model�Լ�˽��Model��Դ�롣ͬ���ģ�����ֻ��Ҫ�˽⼴�������Դ�룬�������Լ���Ҫʵ�����ѵ�Model��

- scripts

  �����ŵ��ļ�Ҳ�Ǻ����ô��ģ����ǹٷ��ṩ��һ��������mesh���ڽӿڵ�python�ű����û�����������Щ�ű�ͨ������ʵ��mesh����Ĵ����Լ�mesh���ݰ����շ����ǳ��ʺ�����Щ��̫���˽�Mesh����ʹ��Mesh���û����������ء�

- tools

  �ô���ŵ���Nordic�ٷ��ṩ��һЩpython�ű����ߣ����ڿ��������Լ�һЩ�ĵ������ɣ���������Ŀǰ��ʱ�ò������������Nordic��������ʱ�������Ŀǰ�ṩ�Ĺ���Ҳ�Ƚ��١�
- ......

  Ҳ��ٷ��Ժ������������ļ��У�����ظ�����ϸ��Ȼ������ֹĿǰΪֹ�����������⼸���ļ��С�

# �ܽ�

Nordic�ٷ���Mesh SDK�������Ϸ���Ļ����Եģ�������һЩ���ݻ��ǿ�������������ģ����û�в鿴 **��README��** �Ļ�����**external**�ļ�����Ҳ�����Э��ջ��������ݣ���**tools**�ļ������ṩ��һЩpython�ű����⿴����ֻ���˽�һ����ţ�����ѹ����֪����ôʹ��:laughing:��ͬ��**scripts**Ҳ�ǣ�û����ص��ĵ�˵�����ʹ����Щ�ű���
      
