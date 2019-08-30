<!--
 * @Description: In User Settings Edit
 * @Author: Helon CHEN
 * @Date: 2019-08-15 21:08:42
 * @LastEditTime: 2019-08-30 22:00:02
 * @LastEditors: Please set LastEditors
 -->
# ǰ��
����ǰ�漸�������½ڵؽ��⣬�����Ŵ�Ҿ��㲻�ܺ���Ϥ���˽�SIG MESH,ҲӦ����һ������֪����ˣ���������ʱ��������ʾ���ʹ��SES�SIG MESH�Ŀ��������ˡ�
# ʲô��SES
SES��[SEGGER Embedded Studio](https://www.segger.com/products/development-tools/embedded-studio/)����д�����С�ཫ��SES����������SES��SEGGER��˾������һ����ƽ̨IDE **(֧��Windows��Linux��MaC OS)**������SEGGER��˾��˭�������˭û����˵������ô���϶���һ����Ƕ��ʽ�ˣ������Ǵ��������ġ��������ֶ��е�JLINK���Թ��߾������ǼҸ�á����û���������������������**IAR��MDK**�ġ�ͬʱ��ʹ��Nordic��BLEоƬ�ǿ������ʹ�����IDE��û�а�Ȩ�ľ��� **(Nordic�ٷ���SEGGER�������Ѿ�̸����)**��
# ǰ��׼��
�����ǿ�ʼ�����֮ǰ�����ǻ���Ҫ�������¹��ߣ�

- [SEGGER Embedded Studio](https://www.segger.com/products/development-tools/embedded-studio/)
- SIG MESH��SDK��
    
    ���ط�ʽ�Ͷ�Ӧ�ķ������Բο�[Nordic MESH SDK �ĵ���ܼ��](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PRIVATE/blob/master/%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86/Nordic%20MESH%20SDK%20%E6%96%87%E6%A1%A3%E6%A1%86%E6%9E%B6%E7%AE%80%E4%BB%8B.md)
- nRF SDK��

    ������ǰ�����µ�����Ӧ��֪����SIG MESH�ǻ��ڵ͹���������һ��Ӧ�ò�Э�飬������ǻ���Ҫ����nRF SDK��**���ǣ�ע��汾��Ҫ����£�Ӧ�ÿ�SIG MESH��SDK����Release Notes**��
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PRIVATE/blob/master/Material%20library/BLE_MESH_Release_Notes.png)

    - SDK����
    
        �ź�����nRF SDK���ƺ�û���ϴ���Github�����ֻ�ܴӹٷ������ˣ����ص�ַ[�����](https://www.nordicsemi.com/Software-and-Tools/Software/nRF5-SDK)
    - ����API�ֲ�

        ���Ҳ��һ���ǳ���Ҫ�����ϣ����Ժܷ���ز��ĸ���API�Ĺ��ܼ�ʹ�÷������������������[�����](http://developer.nordicsemi.com/nRF5_SDK/)����Ȼ��������������̫�鷳���������أ���Ҳ���������Ǻ���ķ������ϲ鿴 **(���ڷ��������ڹ��ڣ����Դ򿪵���Ӧ�ٶȻ�ܿ�)**�����������[�����](http://nordic.wireless-tech.cn/nrf5/index.html)
# �����
������SIG MESH�Լ�nRF SDK������֮�����߿��Բ��÷���ͬһ��·������Ŀ¼�£����Ǳ˴��໥�����ֻ�������������Ϊ����֪����SIG MESH�ǻ��ڵ͹���������һ��Ӧ�ò�Э�飬��ô�������������֮����������أ�����Ĳ������£�

1. ʹ��SES��SIG MESH��ʾ�����̣�����С����**light_switch_server**Ϊ����
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PRIVATE/blob/master/Material%20library/light_switch_server_nrf52840.png)

2. <code>Tools</code>--><code>options</code>--><code>Building</code>--><code>Golbal Macros</code>�������ѡ�����nRF SDK�������ľ���·����������ʾ **(������С��ĵ�ַ�����߿��Ը����Լ���·������Ӧ���޸ģ�ע����б������б��֮��)**��
    ```c
    F:/Bluetooth/Nordic/SDK/nRF5_SDK_15.3.0_59ac345
    ```
3. �������Ĳ���֮�����������ȷ�Ļ���ô��ʱ�Ϳ���ֱ�ӱ���SIG MESH�������е�ʾ�������ˡ�

Ϊ�˸��������˵�ȥ���������Ĳ������뿴��ͼ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PRIVATE/blob/master/Material%20library/Global_Macro_Setting.gif)
    
# ���
�����ڽ�β��������Ҫ����һ�¹����ߵľ��ǣ�����Ĳ���������������Ҫ��ǰ���ص͹�������Э��ջ�ģ�������SIG MESH��صĴ���֮ǰ����Ҫ��������SoftDevice����һ����Ҫ���ע��һ�µġ�