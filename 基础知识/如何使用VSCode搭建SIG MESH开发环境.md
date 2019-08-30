<!--
 * @Description: In User Settings Edit
 * @Author: Helon CHEN
 * @Date: 2019-08-17 13:36:51
 * @LastEditTime: 2019-08-30 22:37:24
 * @LastEditors: Please set LastEditors
 -->
# ǰ��
����һ�½ڽ�����**���ʹ��SES�SIG MESH��������**�������Ŵ󲿷��˶��Ѿ���������ʹ��SES��ʼ�Լ���SIG MESH֮���ˡ�Ȼ�����˴�С��ȴ����ƫ�����**CMake+Vscode+nRF5-SDK-for-Mesh**���������˴�MESH�Ŀ�����������ˣ����½ڽ��ʺ���һ���������ֽ�ȡ���ˣ��Ӷ�Ҳ��̫�ʺ�ɶ��Ҫ�ֳɵĹ���ʦ **������еĻ�����������Ϳ����ƶ������굽���Ͻǣ���������** ���ȣ�������������Ϸ�ʽ��ҵ�ڲ��������״Σ����������Ѿ�������������Ƶ����¡�Ȼ����������ǻ��ڴ�Ӧ�ò��Ӧ�ã���û�и�Ӳ������һ�����س�����ֻ�����ǵļ�ƪ��Ƕ��ʽ������صģ����С����û����б�Ҫ�������Ļ���дһд�ģ�˳���ٽ��Լ��ĳɳ���

# ����
��ô��������ϵķ�ʽ��ʲô���������أ�С����Ϊ�����¼��֣�

1. ��Դ��ѣ�û�а�Ȩ���ס���ΪCMake�Լ�Vscode���ǿ�Դ��ѵĹ��������
2. �ʺ���ģ�黯�Լ�����Ŀ���̿����ҿ�ƽ̨������ƽ̨���ƣ�
3. ��������ʦ�����ˮƽ�����˽�����ԭ��

# ȱ��
����Ŀǰ���˽⣬�������ŵ��ż��е��֮��Ҳû��ʲô������ȱ���ˡ���Ȼ�ˣ����ɻ���IDE�ڵ��Է��滹�ǻ��������ַ�ʽ�ġ�

# ׼������
�ڿ�ʼ�����֮ǰ�����ǻ���Ҫ��װ���µĹ��������

| �������� | ���� |
|-----|-----|
| [nRF5x Command Line Tools](https://www.nordicsemi.com/Software-and-Tools/Development-Tools/nRF-Command-Line-Tools/Download#infotabs) | ���������Լ��ϲ��̼�����װʱӦ�ý�����ӵ�ϵͳ������������ѡ    |
| [SEGGER J-Link](https://www.segger.com/downloads/jlink) | ���ڴ�����ԣ���ѡ    |
| [Python 2.7](https://www.python.org/downloads/) | ��������OTA�̼������python�ű�����װʱӦ�ý�����ӵ�ϵͳ������������ѡ    |
| [Python 3.5](https://www.python.org/downloads/) | �����������ػ��ߺϲ��̼�����ؽű�����װʱӦ�ý�����ӵ�ϵͳ������������32Bit�İ�װ��������3.5.1�汾���ϣ���**�˴�Ҫע�⣺��װʱӦ���䰲װ���̷��ĸ�Ŀ¼�£�������Python2.7��ͻ**����ѡ    |
| [CMake](https://cmake.org/download/) | �������ɱ��صĹ����ļ�����װʱӦ�ý�����ӵ�ϵͳ�������������°汾���ɣ�����ѡ    |
| [Ninja](https://github.com/ninja-build/ninja/releases) | ����CMake���ɵı��ع����ļ�������Ӧ��Hex��ELF��MAP���ļ����ֶ�������ӵ�ϵͳ�������������°汾���ɣ�����ѡ    |
| [GNU ARM Embedded Toolchain](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads/) | ������������**7-2018-q2-update (7.3.1)** �������汾�Ĳ�Ҫ���أ���װʱ������ӵ�ϵͳ������������ѡ    |
| [Doxygen](http://www.doxygen.nl/)��[Graphviz](http://www.graphviz.org/)��[Mscgen](http://www.mcternan.me.uk/mscgen/)| �����Ҫ�������ߵ�nRF5-SDK-for-Mesh API�ĵ���ͱ����������������(Ŀǰ�ٷ���û���ṩ�ֳɵ�API�ֲᣬ��ô��ֻ���Լ�������)���������������Ҫ��ӵ�ϵͳ������������ѡ    |
| [Visual Studio Code](https://code.visualstudio.com/)| **Cortex Debug���**����ѡ��**CMake��CMake Tools��CMake Tools Helper���**����ѡ    |

���������ᵽ�����֮�⣬��Ȼ�㻹Ҫ���� **[nRF5-SDK-for-Mesh]((https://www.nordicsemi.com/Software-and-Tools/Software/nRF5-SDK-for-Mesh/Download#infotabs))** �� **[nRF5-SDK]((https://www.nordicsemi.com/Software-and-Tools/Software/nRF5-SDK))** ����SDK��������

# �����
��װ�����������֮�����ǾͿ���ֱ����Visual Studio Code��nRF5-SDK-for-Mesh�ˣ�������ʾ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/open_nRF5_SDK_for_Mesh_with_vscode.gif)

ͬʱ����֮����Ҫ��װ�����ἰ����Visual Studio Code�����
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Extensions_for_debug.png)

## ����Cortex Debug���
�ò����Ҫ��ʹ����Visual Studio Code�е���Cortex-M�ں˵�MCU����һ���ǳ�����Ĳ������������ʹ�õ���JLINK���Է���������������Ҫ��������������JLINK��λ�ã����������ٰ���F5ʱ����Ż����JLINK��GDB�����е��ԡ�Ϊʵ�������Ŀ�ģ����ǿ�����������<code>Manage</code>--><code>Settings</code>--><code>Extensions</code>--><code>Cortex-Debug Configuration</code>--><code>JLink GDBServer Path</code>--><code>Edit in settings.json</code>,Ȼ������Լ���JLinkGDBServerCL��·����������С���·��
```c
C:\\Program Files (x86)\\SEGGER\\JLink\\JLinkGDBServerCL.exe
```
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Cortex_Debug_Configuration.gif)

������������֮�����ǻ���Ҫ�����������ǵ�ǰ���Ե���ʲô�ͺŵ�MCU��ʲô���Խӿڵȵȣ�ֻ����Щ������˲���������ʹ�øò����������С����������ݣ�����Ĳ����뿴���µĶ�ͼ��
```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [            
        {
        "cwd": "${workspaceRoot}",
        "executable": "${workspaceRoot}/build/examples/beaconing/beaconing_nrf52840_xxAA_s140_6.1.1.elf",// ����������������Լ���ʵ��·��,�����ҽ����ҵ�ǰ��ʾʱʹ�õ�ʾ������
        "name": "Debug Microcontroller",
        "request": "launch",
        "type": "cortex-debug",
        "servertype": "jlink",//���Է�������ѡ��,����֧��opennocd��pyocd��pe�Լ�stutil
        "runToMain": true,//һ���Ծ�ͣ��main����
        "device": "nRF52840_xxAA",//�豸���ͺ�
        "interface": "swd",//SWD�ӿ�
        "ipAddress": null,
        "serialNumber": null, 
        },
    ]
}
```
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Cortex_Debug_Configuration_Json.gif)

## ����
������������֮�󣬽��������Ǿ�Ҫ����CMake�Թ��̽��б��벢����ELF��HEX���ļ��ˡ����ǣ��������ǽ����������nRF52840_xxAA��Ȼ������Ĭ�ϵ���nRF52832_xxAA���������ǻ�Ҫ�޸�һ����ص��ļ�������ͼ��ʾ��

![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/modification_for_platform_cmake.png)

ֻ�����ʱ�����ǲſ��������ضԹ��̽��б��룬����Ĳ������£�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/CMake_build_project.gif)

Ȼ�����ǾͿ����ڸ�Ŀ¼�����½���һ��**build**�ļ��С�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/project_builded.png)

## ��������
�������֮�󣬴�ʱӦ�þͻ�������Ӧ��ELF��HEX���ļ��ˣ���ô�������ʱ��Ϳ�������Cortex Debug������е������أ�����Ĳ����뿴���µĶ�ͼ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/project_debug.gif)

## �������nRF5-SDK-for-Mesh�����ֲ�
Ŀǰ���ٷ���û�а�nRF5-SDK-for-Mesh�����ֲ���ڹٷ��ķ������ϣ����ǽ����ɵķ������������ǣ�Ŀǰ����Ҳ�㲻���׹ٷ����뷨�����ǣ�û�й�ϵ���ǰ��չٷ��ķ�������Ҳ�ǿ��Եõ��ģ�����Ĳ���������ʾ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/doc_generation.gif)

������ǿ�����**build**�ļ����£��ҵ����ɵ������ļ���
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/doc_generation.png)