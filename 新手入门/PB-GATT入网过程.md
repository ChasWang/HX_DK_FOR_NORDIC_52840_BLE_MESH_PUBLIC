<!--
 * @Description: In User Settings Edit
 * @Author: ��ʱ��
 * @Date: 2019-08-31 19:49:08
 * @LastEditTime: 2019-12-16 13:56:39
 * @LastEditors: Please set LastEditors
 -->
# ǰ��
��������ǰ��ļ����½����ݿ�֪��Ŀǰ����ͨ�����ַ�ʽ��������������

- PB-GATT

    ��Ҫ������Щ���߱�PB-ADV���Ե��豸����ӵؼ���SIG Mesh���磬���ֻ���ƽ����Եȵȣ�ǰ����δ�������õ��豸��Unprovisioned device,ʹ����proxy���ԣ�
- PB-ADV

    ͨ��ADV���صķ�ʽ����δ�������õ��豸����SIG Mesh���磬������Я����SIG MeshЭ��ջ���豸��

��ô�����½���Ҫ�������ͨ��PB-GATT�ķ�ʽ����unprovisioned device����SIG Mesh���硣����PB-ADV��صĻ��⣬���Ƿ�����һ�½ڽ�����⡣

![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Let's_start.png)

# ��������
��SIG Mesh���������̣���������ֻ֪�����µ�������ۣ�

- ����Beacon�ź�
- ����
- ����������Կ
- ��֤
- �����������ݷַ�

![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_Behavior.png)

Ȼ������ʵ��ʹ������Щ������ϸ���ɺܶ�С��ϸ�ڡ���ô����ЩϸС��ϸ�ڵ���������ô���ģ���������ͼ��ʾ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/The_process_for_provisioning.png)

����ͼ��֪�����������Ĺ��̻��ǱȽϸ����ˣ�������ô�ཻ������Ϊ�����յ�**provisioning data**�е�ֵ����new device��provisioner����provisioning complete PDU֮��new device������ת��ΪNode�����������������Ҷ���ţһ��һ���ȥ�ҿ����ǵ�����Ŀ��
## Mesh Proxy Service
�ڿ�ʼ�����������������֮ǰ��С����û����б�Ҫ���˽�һ��ʲô��mesh proxy service���÷�����Ҫ����������ֵ��
- mesh proxy data in

    ������ֵ��Ҫ����provisioner��new device����node������ص�PDU
- mesh proxy data out
    
    ������ֵ��Ҫ����new device����node������ص�PDU��provisioner

Ϊ����������������������⣬���ǿ��Բ鿴��ͼ��������mesh proxy service�Ĺ���ԭ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_proxy_service.png)

���������ǿ��Ժ�������˽⵽��������**provisioning PDU**����**Mesh Network PDU**������ͨ��**mesh proxy data in**�������ֵ������Ӧ��PDU��new device����node����Ȼ��Ҳ����ͨ��**mesh proxy data out**�������ֵ������Ӧ��PDU��**provisioner**����ô������������ֵ���������ἰ��PDU֮�⣬�����ܴ�����Щ���͵�PDU�أ���Ȼ��С����ô˵��ô�Ϳ϶��ǲ�ֹ��������������PDU�����԰�:smile:����ʵ����mesh proxy service�ǿ��Դ������¼������͵�PDU��

- Network PDU
- Mesh Beacon
- Proxy Configuration
- Provisioning PDU

����**Mesh Beacon**��Node-->provisioner����**mesh secure network beacon**����**Proxy Configuration**��������Proxy Client��Proxy Server֮�佻��Proxy������Ϣ����Ҫ���ڽ�Ŀ���ַ���������������ߺ�����,��Ӱ������ͺ��������Ƴ����𵽹��˵����á�
### Proxy PDU
Proxy�ͻ���ͨ��Proxy PDU��Proxy����˽������ݽ���������������Proxy PDUs���԰���**Network PDUs**��**mesh beacons**��**proxy configuration messages**����**Provisioning PDUs**��ͬʱ����һ��Proxy PDU���԰���һ֡���������ݣ�Ҳ�����Ƿְ������ݣ�**����һ��Ҫע�⣡������Proxy PDU�ĳ��ȴ�С�Ǹ���ATT_MTU��������**���������������ǿ���Proxy PDU������Ŀ����ô���ģ����ǣ����½���Ҫ����**Provisioning PDUs**��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Proxy_PDU.png)

����ͼ��֪��Proxy PDU�������ֶ���ɣ�
- SAR
- Type
- Data
#### SAR
�տ�ʼ��������ֶΣ����������˶���������京�塣��Ϊ������Ѳ²�õ���ȫ����ɶ����ʵ����ȫ�ƾ���**Message segmentation and reassembly**�����ҿ���ȫ��֮��ͺ��������������Ȼ��������ָʾ��ǰ�����ݰ���һ֡�����İ����Ƿְ�����ô���ְ���������Ӧ����α����أ�

| Value | Description |
|-----|-----|
|0b00|Data field contains a complete message|
|0b01|Data field contains the first segment of a message|
|0b10|Data field contains a continuation segment of a message|
|0b11|Data field contains the last segment of a message|

���ϱ��֪��������һ֡��ʱ����0b00���ְ��ĵ�һ��֡����0b01���м��֡������0b10������һ֡����0b11�����ʱ�����������ˣ���������̫�����ˣ���ô��ʵ����������ô�����أ�

- ������һ֡

    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Complete_Mesh_Proxy_PDU.png)
- ���֡��

    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Segmentation_Mesh_Proxy_PDU_1.png)
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Segmentation_Mesh_Proxy_PDU_2.png)
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Segmentation_Mesh_Proxy_PDU_3.png)
#### Type
����ֶξ��Ǳ�����ǰЯ����PDU��ʲô���͵ģ�Ҳ������ǰ����˵��Proxy PDU�ܴ����ļ������͵����ݣ�

| Type | Name |
|-----|-----|
|0x00|Network PDU|
|0x01|Mesh Beacon|
|0x02|Proxy Configuration|
|0x03|Provisioning PDU|
#### Data
���ֶθ���Type�����ͣ�Ȼ���������Ӧ�����ݡ����ǣ��������������̶���Provisioning PDU����Provisioning PDU�ַֺü������ͣ�

| Type | Name |
|-----|-----|
|0x00|Provisioning Invite|
|0x01|Provisioning Capabilities|
|0x02|Provisioning Start|
|0x03|Provisioning Public Key|
|0x04|Provisioning Input Complete|
|0x05|Provisioning Confirmation|
|0x06|Provisioning Random|
|0x07|Provisioning Data|
|0x08|Provisioning Complete|
|0x09|Provisioning Failed|
|0x0A-0xFF|RFU|
### Provisioning PDU
��PDU����Ҫ����provisioner��new device�Ľ����������֡��ʽ���£�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_PDU.png)  

��ͼ��ʾ�ľ�������Provisioning PDU��֡��ʽ���������������������õ�������֡���͡�

- Padding

    �̶�Ϊ0b00������ֵ����ֹʹ�ã�
- Type

    �˴�����ϸ��������ɲ鿴������[Data](#Data)�½ڣ�
- Parameters

    ���ֶ������������**Type**�������Ӧ�Ĳ�����
    
## ����Beacon�ź�
�����������˻���û���������豸�������ⷢ��Beacon�źš�Ψһ�Ĳ�ͬ���ǣ�
- ����֮����豸���ͳ�������Secure Network Beacon
- δ�������豸���ͳ�������Unprovisioned Device Beacon

������Beacon֡��ʽ����������ƪ�²���ϸ����С���Ѿ�����һƪ��[Mesh Beacon֡��ʽ](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/%E6%96%B0%E6%89%8B%E5%85%A5%E9%97%A8/Mesh%20Beacon%E5%B8%A7%E6%A0%BC%E5%BC%8F.md)�н����ˡ�
## ����
���������provisioner��������ģ����䷢�ֶԶ��豸��unprovisioned deviceʱ�������δ�������豸�������룻����������������裺
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_invitation.png)
### Provisioning Invite
���ȣ�provisionerͨ��**mesh proxy data in**����ֵ��Write Command����ʽд��**Provisioning Invite PDU**�������͵�֡���ݽ�����**attention time**�����Ǹ���new deviceһ��ʱ��ֵ��Ȼ�������κο��������ܱ�����ע��Ķ���ʱ��Ϊ**attention time**�룬�����֡��ʽ���£�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_Invite_PDU.png)

### Provisioning Capabilities
��PDU��new device����provisioner�ģ����ݻ�Ƚϸ��ӣ���Ҫ�����ڸ���provisioner��new device�߱���Щ��������Щ����Ҳ��Ӱ���ź�����һ���ж������繫Կ�Ľ�������֤�ȵȡ���ô���Ǿ�������Щ�����أ��뿴�±�������

| Field | Size(octets) |Notes|
|-----|-----|-----|
|Number of Elements|1|Number of elements supported by the device|
|Algorithms|2|Supported algorithms and other capabilities|
|Public Key Type|1|Supported public key types|
|Static OOB Type|1|Supported static OOB Types|
|Output OOB Size|1|Maximum size of Output OOB supported|
|Output OOB Action|2|Supported Output OOB Actions|
|Input OOB Size|1|Maximum size in octets of Input OOB supported|
|Input OOB Action|2|Supported Input OOB Actions|

���ϱ��֪���漰��������Ҫ������OOB�ķ�ʽ��������Ҳ��������ǽ��������Ǿͷֱ𿴿���������ʾ�Ĺ��ܡ�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_Capabilities_PDU.png)  
#### Number of Elements
��Ȼ����ֶ�����ʾ���ǵ�ǰ���new device�߱����ٸ�Ԫ�أ�����new device��������һ��Ԫ��,����255��������ʲô��Ԫ�أ����Բο�С���ϼ����½�д��[ʲô��Element��Model](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86/%E4%BB%80%E4%B9%88%E6%98%AFElement%E5%92%8CModel.md)

| Value | Description|
|-----|-----|
|0x00|Prohibited|
|0x01�C0xFF|The number of elements supported by the device|

#### Algorithms
����˼�壬���ֶα�ʾnew device֧����һ�ּ����㷨��Ȼ��ĿǰΪֹ����֧��**FIPS P-256 Elliptic Curve**�㷨�����SIG�ٷ�Ӧ�û��Ƴ�����ļ����㷨��

| Bit | Description|
|-----|-----|
|0|FIPS P-256 Elliptic Curve|
|1-15|Reserved for Future Use|

#### Public Key Type
���ֶα�ʾ��ǰ��new device֧��ʲô���͵Ĺ�Կ��ĿǰΪֹ����֧��OOB��ʽ�Ĺ�Կ����Ҳ����˵��Կ����ͨ��OOB��ʽ��provisioner���н�������֪�����߻���û��ӡ�������ǵ�[Mesh Beacon֡��ʽ](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/%E6%96%B0%E6%89%8B%E5%85%A5%E9%97%A8/Mesh%20Beacon%E5%B8%A7%E6%A0%BC%E5%BC%8F.md)�����ἰ��**OOB Information**����Щ��Ϣ���Ǹ��ߴ�ҿ��Բ������ַ�ʽ�����ݹ�Կ����Ȼ����Ҳ��ǿ��Ҫ����Ҳ���Բ���OOB�ķ�ʽ�����ݹ�Կ������ʹ��������ɵĹ�Կ��ͬʱ����Կ�ĳ���ȡ������ѡ�õļ����㷨�������������ҽ���ѡ��**FIPS P-256 Elliptic Curve**�㷨������Կ�ĳ��Ⱦ���**32�ֽ�** **(������չʾ��Traces����δ����OOB)**��
- OOB Information

    | Bit | Description |
    |-----|-----|
    | 0 | Other    |
    | 1 | Electronic / URI    |
    | 2 | 2D machine-readable code    |
    | 3 | Bar code    |
    | 4 | Near Field Communication (NFC)    |
    | 5 | Number    |
    | 6 | String    |
    | 7 | Reserved for Future Use    |
    | 8 | Reserved for Future Use    |
    | 9 | Reserved for Future Use    |
    | 10 | Reserved for Future Use    |
    | 11 | On box    |
    | 12 | Inside box    |
    | 13 | On piece of paper    |
    | 14 | Inside manual    |
    | 15 | On device    |

- Public Key Type values

    | Bit | Description|
    |-----|-----|
    |0|Public Key OOB information available|
    |1-7|Prohibited|

#### Static OOB Type
ͬ���ģ�����ֶ�����������new deviceʹ��ʲô�����͵ľ�̬OOB���ں�̵���֤����[Public Key Type](#Public-Key-Type)һ������Ҳ����ǿ�Ƶģ���Ҳ���Բ����þ�̬OOB�ķ�ʽ��֤�������������Firmware�ж�����Դ��16�ֽڵľ�̬OOB�����飻û����̬OOB����󳤶���16�ֽڡ��ӱ�ʵ���е�׽��Trace�У����Կ��������������ں����֤�ľ�̬OOB�ģ���������������ʱ��û��ʹ������

| Bit | Description|
|-----|-----|
|0|Static OOB information available|
|1-7|Prohibited|

#### Output OOB Size
���������ǾͿ��Բ²������������OOB�Ĵ�С��**���ֶ���Ҫ�Ƕ����˿������(���磬��ʾ��������˵����)���ֻ�����ĸʱ��λ��**�������������ĸ�����֡���ĸ�����Ǹ�����[Output OOB Action](#Output-OOB-Action)�ֶ����õ���������ģ���ô���ļ�������أ�������һ����������

- Output Numeric
- Output Alphanumeric
- ��˸
- ����
- ��

��ô����������ܶ��߻��� **��������OOB�Ĵ�С����Ƕ����أ���**����������ǿ������±����ҵ���

| Value | Description|
|-----|-----|
|0x00|The device does not support output OOB|
|0x01�C0x08|Maximum size of Output OOB supported by the device|
|0x09�C0xFF|Reserved for Future Use|

���ڣ�**Output Numeric**��**Output Alphanumeric**�ķ�ʽ���Ǻܺ���⣬����**Output OOB Size**�Ĵ�С������Ӧ��λ�������磺**Output OOB Size**����Ϊ7����ô��������ֻ������ִ�д��ĸ��ϵ�λ������7���� **��1234567�����ߡ�123ABCD��**��������Ҫע����ǣ�����Щֵ����ȫ������**�ַ���**�������Output OOB Action�ֶ��е�ֵ����������������֮һ��new device�����**Output OOB Size**��ֵ��1~**Output OOB Size**�������ѡ��һ�����֣�Ȼ��ѡ�еĶ�����Ӧ��ʱ��������Ĵ�����provisioner��ӻ�ȡ�õ����������֣������������ǿ��Բ���[Authentication Method��Action��Size](#authentication-method��Action��Size)�½��е����������
#### Output OOB Action
����Output OOB Action���±���ʾ��

| Bit | Description|Data Type|
|-----|-----|-----|
|0|Blink|Numeric|
|1|Beep|Numeric|
|2|Vibrate|Numeric|
|3|Output Numeric|Numeric|
|4|Output Alphanumeric|Alphanumeric|
|5-15|Reserved for Future Use|n/a|

#### Input OOB Size
����������[Output OOB Size](#Output-OOB-Size)��������һģһ���ģ��޷Ǿ��ǽ������Ϊ���롣���⣬������ɰ�ѹ��š��

| Value | Description|
|-----|-----|
|0x00|The device does not support Input OOB|
|0x01�C0x08|Maximum size of Input OOB supported by the device|
|0x09�C0xFF|Reserved for Future Use|

#### Input OOB Action
ͬ��֧�ֵ�����OOB�������±���ʾ��

| Bit | Description|Data Type|
|-----|-----|-----|
|0|Push|Numeric|
|1|Twist|Numeric|
|2|Input Numeric|Numeric|
|3|Input Alphanumeric|Alphanumeric|
|4-15|Reserved for Future Use|n/a|

����OOB��صģ����˹�Կ֮�⣬�������ں�������֤�ķ�ʽ�ṩ�˲�ͬ�ķ�����

## ������Կ
��������Ĳ���֮��provisioner�Ѿ�֪��new device�߱���Щ�����ˣ���ôprovisioner�ͻ����new device��Ӧ�������������Ӧ���͵Ĺ�Կ����������һ�㣬��Ҫע�µ��ǣ������Ӧ��**Provisioning Capabilities PDU**�еļ����㷨provisioner��֧�֣���provisioner��ѡ������֧�ֵİ�ȫ����ߵļ����㷨����ô���ڽ�����Կ�������������������������Щ�����أ������������Ǹ���С��ħ��Ĳ������ƣ�
### Provisioning start
��������[������Կ](#������Կ)���Ժ�������˽⵽����PDU��provisioner����[Provisioning Capabilities PDU](#provisioning-capabilities)�е�ѡ�������Ӧ�����ݸ�new device��������������Ҫ�������ַ�ʽ���й�Կ�����Լ����ú�����֤��ʽ��ͬʱ��new device�յ���PDU֮�����Ὣ**Attention Timer**����Ϊ0�������֡��ʽ���±���ʾ��

| Field | Size(octets)|Notes|
|-----|-----|-----|
|Algorithm|1|The algorithm used for provisioning|
|Public Key|1|Public Key used|
|Authentication Method|1|Authentication Method used|
|Authentication Action|1|Selected Output OOB Action or Input OOB Action or 0x00|
|Authentication Size|1|Size of the Output OOB used or size of the Input OOB used or 0x00|

���������˸�PDU�����ֶεĺ��壬��ô����ʵ����������������������ʲô��ʽ���ֵ��أ�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_Start.png)

�ǲ��Ǹ���������е�����һģһ��������˵SIG MeshҲ����ʲôħ������Ҳ���б�׼��ѭ�ġ�
#### Algorithm
����������ֶ�������������ʲô���͵ļ����㷨������Ŀǰ�ƺ�Ҳû��ѡ��ֻ��ѡ��**FIPS P-256 Elliptic Curve**��

| Value | Description|
|-----|-----|
|0x00|FIPS P-256 Elliptic Curve|
|0x01�C0xFF|Reserved for Future Use|

#### Public Key
���ֶβ������������Public Key���ݵģ�����������ʾ�Ƿ�ʹ��OOB��ʽ��Public Key������ǣ���ô��ʹ��OOB�ķ�ʽ����Public Key���� **(ʹ��FIPS P-256 Elliptic Curve�����㷨�Ļ�����32�ֽ�)**������������ɡ�������������£�

| Value | Description|
|-----|-----|
|0x00|No OOB Public Key is used |
|0x01|OOB Public Key is used|
|0x02�C0xFF|Prohibited|

��ô��ʹ�úͲ�ʹ��OOB Public Key�������������أ����ǿ��Բ鿴��ͼ��ʾ��

- No OOB Public Key is used
    
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Start_without_OOB_Public_Key.png)
    
    ����ͼ��֪�������ʹ��OOB��ʽ�Ĺ�Կ����ô��Կ��provisioner��new device���Բ������໥������
- OOB Public Key is used

    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Start_using_OOB_Public_Key.png)  
    �����ʹ����OOB��ʽ�Ĺ�Կ����ôprovisionerͨ��OOB�ķ�ʽ��new device��ȡ�õ���Կ��Ȼ��provisioner��������һ����Կ�ٴ��͸�new device����new device��ʱ�����ٴ���Կ��provisioner�ˣ���Ϊprovisioner�Ѿ�ͨ��OOB�ķ�ʽ��ȡ�õ�new device�Ĺ�Կ�ˣ�

������provisioner����new device��Ҫ���鹫Կ����Ч�ԣ������Ч����ʹ�ù�Կͨ������Ĺ�ʽ����ó�**ECDHSecret**��
> ECDHSecret = P-256(private key, peer public key)

����˴���������ʧ�ܡ�  
#### Authentication Method��Action��Size
���������⼸���ֶθ�������[Static OOB Type](#Static-OOB-Type)��[Output OOB Action](#Output-OOB-Action)��[Input OOB Action](#Input-OOB-Action)���໥��Ӧ�ģ���Ҳ����˵���ֶ��ø���new device��Ӧ��[Provisioning Capabilities PDU](#Provisioning-Capabilities)���ݣ�������Ӧ�����ݣ������Authentication Method���������±���ʾ��

| Value | Description|
|-----|-----|
|0x00|No OOB authentication is used |
|0x01|Static OOB authentication is used|
|0x02|Output OOB authentication is used|
|0x03|Input OOB authentication is used|
|0x04-0xFF|Prohibited|

�����ϱ�����ݣ���ô�������¼�����ϣ�

- 0x00
    
    Authentication Action��Size�ֶε����ݾ�Ϊ0x00����[Provisioning start](#provisioning-start)�½��еĽ�ͼ��ʾ��
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Authentication_with_static_OOB_or_no_OOB.png)

    ���ǿ��Դ�������UMLͼ��������ؿ��������ʹ��No OOB�ķ�ʽ�Ļ�����û����Input��Output�Ĺ��̣�����Ҳ���Ժ������ŵ�˵���������û�о�����֤�ģ���Ϊ��ʱ��authentication Valueȫ��0x00��˫��ֱ�ӽ���**Provisioning Confirmation PDU**��������ô��PDU��ʲô�أ����ǿ����������[Provisioning Confirmation](#provisioning-confirmation)�ҵ���;
- 0x01
    
    ͬ����,Authentication Action��Size�ֶε�����Ҳ�Ǿ�Ϊ0x00��������Ψһ��ͬ���Ǵ�ʱʹ�õ��Ǿ�̬��OOB��ʽ������Firmware����ǰ�����16�ֽڵľ�̬OOB���飬������һ�㣬�����������[Static OOB Type](#static-OOB-Type)�Ѿ��������ˣ���������̽���ͬ��ͼ��ʾ��
- 0x02

    - Authentication Action���������±������

        | Value | Description|
        |-----|-----|
        |0x00|Blink|
        |0x01|Beep|
        |0x02|Vibrate|
        |0x03|Output Numeric|
        |0x04|Output Alphanumeric|
        |0x05-0xFF|Reserved for Future Use|
    - Authentication Size���������±������

        | Value | Description|
        |-----|-----|
        |0x00|Prohibited|
        |0x01�C0x08|The Output OOB Size to be used|
        |0x09�C0xFF|Reserved for Future Use|
    �����ϣ���[Output OOB Action](#Output-OOB-Action)��[Output OOB Size](#Output-OOB-Size)��������һģһ���ġ�
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Authentication_with_Output_OOB.png)

    �����ִ�е�������裬С����û��Ǿ����б�Ҫȥ����һ�µģ��������Authentication Action��Blink��Beep�Լ�Vibrate���е�һ��,��ô����new device��1-**Output OOB Size**�������ѡȡһ�����ֲ�ͨ����ѡ�е�Actionȥ���������֣����磬new device��һ������LEDָʾ�Ƶ���������ô��Authentication action����Blink������������ֵķ�������ͨ����˸�Ĵ���ȥ��Provisioner����new device��1-**Output OOB Size**����ѡ�е�����������authentication action��Output Numeric����Output Alphanumeric����ônew device�����authentication size��ֵ������Ӧ�����Ĵ�д��ĸ�������ֻ�����ĸ�����ֻ�ϡ�
- 0x03

    - Authentication Action���������±������

        | Value | Description|
        |-----|-----|
        |0x00|Push|
        |0x01|Twist|
        |0x02|Input Numeric|
        |0x03|Input Alphanumeric|
        |0x04-0xFF|Reserved for Future Use|
    - Authentication Size���������±������

        | Value | Description|
        |-----|-----|
        |0x00|Prohibited|
        |0x01�C0x08|The Input OOB Size to be used|
        |0x09�C0xFF|Reserved for Future Use|
    ͬ���ģ���[Input OOB Action](#Input-OOB-Action)��[Input OOB Size](#Input-OOB-Size)��������һģһ���ġ�
    ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Authentication_with_Input_OOB.png)
    
    ����������������ĺ���������Output OOB authentication�ǻ���һ�µġ�ֻ��������������ѣ�

����Ҳ���ٴ�֤��[Provisioning Capabilities PDU](#Provisioning-Capabilities)�е����ݾ����˹�Կ���ͺ���֤�ķ�ʽ����Ȼ�������ﻹû�е���֤�Ľ׶Σ�ֻ��Provisioner����new device,�Ҹ������**Provisioning Capabilities PDU**��������������ʲô���ͷ�ʽ����֤��

### Provisioning Public Key
��ʱ��Provisioner��new device�����໥����Ҫ��ECDH�������õ��Ĺ�Կ����PDU��ʽ������ʾ��

| Field | Size(octets)|Notes|
|-----|-----|-----|
|Public Key X |32|The X component of public key for the FIPS P-256 algorithm|
|Public Key Y|32|The Y component of public key for the FIPS P-256 algorithm|

## ��֤
[������Կ](#������Կ)�е��½ڿ�֪��������ǽ����˹�Կ�Ľ����Լ���֤��ʽ��ѡ�������ǣ���δ������֤�Ķ�������ô��֤�Ļ��������ļ���������أ�

### Provisioning Input Complete
��new device�����֤���ֵ�����֮�󣬻���provisioner���͸�PDU��Ȼ������������ô�����أ����ǿ��Բο�[Authentication Method��Action��Size�½���0x03��ʾ������](#Authentication-method��action��Size)��ͬʱ������ҲҪע�⣬��PDU�ǲ�Я���κβ����ġ�

### Provisioning Confirmation
Provisioner��new device����Խ�ĿǰΪֹ�����Ѿ���������PDU **���������͵ĺͽ��յ��ģ���Provisioning_Invite_PDU��Provisioning_Capabilities_PDU��Provisioning_Start_PDU��Provisioning_Public_key_PDU������Ҫע����ǽ�����PDU������֡ͷ�����ͣ���Invite��Capabilities�ȵȣ�**,����OOB��ֵ֤�Լ���δ���ͳ�����������������Ǽ���֮���ϣ��ֵ���ͶԶ��豸���Ա������һ����ȷ�ϣ����Ǹ�PDU����˵��confirmation��ʵ���仹������ȫ��ȷ�ϡ�������Ȼ��Ҫ֪���Է������������ȷ�Ϸ��͵�Confirmation�Ƿ�ƥ�䡣��PDU��֡��ʽ�Ƚϼ򵥣�������ʾ��

| Field | Size(octets)|Notes|
|-----|-----|-----|
|Confirmation|16|The values exchanged so far including the OOB Authentication value|

### Provisioning Random
��[Provisioning Confirmation](#provisioning-confirmation)������ֻ�е�Provisioner��new device˫���յ���PDU����У��ȷ��ֵ��ͬ������PDUҲ�Ǻܼ򵥣�

| Field | Size(octets)|Notes|
|-----|-----|-----|
|Random|16|The final input to the confirmation|

���ˣ���֤�����Ѿ�����ˣ���ô��provisioner���Ը�new device�������������ˡ�

## �������ݷַ�
�������������ʱ�������������ɹ�ֻʣ�����һ���ˡ�ֻҪnew device��ȡ�õ��������ݣ����Ϳ�����new device��node�Ļ���ת����ô�ò�����Ҫ��������Щ�����أ�

### Provisioning Data
ͨ����֤֮��provisioner�Ὣprovisioning data����new device,�������е����ݶ���ͨ��**�Ự��Կ**���ܵģ����Ự��Կ������������������˵��**ECDHSecret**����ô��PDU������Щ�����أ�������������֡��ʽ����ô���ġ�

| Field | Size(octets)|Notes|
|-----|-----|-----|
|Encrypted Provisioning Data|25|An encrypted and authenticated network key, NetKey Index, Key Refresh Flag, IV Update Flag, current value of the IV Index, and unicast address of the primary element|
|Provisioning Data MIC|8|PDU Integrity Check value|

���ȣ�ӳ���������Ǽ�������֤����������Կ�Լ��������ȵ����ݣ���Щȫ�������ǽ�����SIG Meshʹ�õ�ͨ��֤������ôС���������׳�һ������ **�����ĳ���Ѿ��������豸�����ˣ���ôͬ�������豸һģһ�����豸�Ƿ����ֱ�ӽ���Щ���ݱ���������Ȼ��ֱ��д�뵽�����δ�������豸���Ӷ��ﵽ���ټ���һ��ָ����SIG Mesh�����أ���** ���ڣ���������Ǻ�̻Ὺר������:smile:���������������ǿ�����Щ������֤�����ݾ��������ʲô��

| Field | Size(octets)|Notes|
|-----|-----|-----|
|Network Key|16|NetKey|
|Key Index|2|Index of the NetKey|
|Flags|1|Flags bitmask|
|IV Index|4|Current value of the IV Index|
|Unicast Address|2|Unicast address of the primary element|


- Network Key

    ����������ʾ������ǵ�������Կ�ˣ�

- Key Index

    �������ʲô�����أ�����������Կ�ĳ�����16�ֽڣ����ֱ����SIG Mesh�����д���16�ֽڵ�������Կ���е㲻̫��ʵ����Ϊ��ԭ������ռ�õ�֡���ݵ�λ�þͲ���������������������Կ����������������Ҫ��������Կ����������ڵ㣬ֻ��ҪҪ��������Կ�������ɡ�ͨ�����������ǿ�����������Կ�б��ȡ���Ӧ��������Կ�������ϸ�ڣ����߿��Բο�**SIG Mesh Spec��4.3.1.1�½�**��
- Flags

    ���ֶλ�ȽϺ���⣬�޷Ǿ���IV Update��Key Refresh��أ�

    | Bits | Definition |
    |-----|-----|
    | 0 | Key Refresh Flag (0: False 1: True)    |
    | 1 | IV Update Flag (0: Normal operation  1: IV Update active)    |
    | 2�C7 | Reserved for Future Use     |

    ������������[Mesh Beacon֡��ʽ](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/%E6%96%B0%E6%89%8B%E5%85%A5%E9%97%A8/Mesh%20Beacon%E5%B8%A7%E6%A0%BC%E5%BC%8F.md)Ҳ���ἰ��

- IV Index

    ���Ҳͬ������⣬��ʾ��ǰ��IV����ֵ����߱������������ܣ�
    1. ����Ӧ�ò�������������֤�ͼ���
    2. ��**Sequence Number**��Ҫ���ʱ������**IV Update**������**IV Index**ֵ���ӣ��Ӷ���ֹ**Sequence Number**���ظ�ʹ��
    
- Unicast Address

    �����ݱ�ʾprovisioner�������ǰ�豸��ҪԪ�صĵ�����ַ��

### Provisioning Complete��Failed
����������͸�������ˣ�����ɹ����յ�������provisioning data,��Щnew device�ͻ���provisioner����provisioning complete PDU��������provisioning failed PDU����Ҫ���ע�����ǰ����û��Я���κεĲ�������������Я���о���Ĵ����� **(1���ֽڵĳ���)**��Ҳ����˵�����ĸ����ڳ��������ˣ�����������ʾ��

| Value | Name|Description|
|-----|-----|-----|
|0x00|Prohibited|Prohibited|
|0x01 |Invalid PDU|The provisioning protocol PDU is not recognized by the device|
|0x02|Invalid Format|The arguments of the protocol PDUs are outside expected values or the length of the PDU is different than expected|
|0x03|Unexpected PDU|The PDU received was not expected at this moment of the procedure|
|0x04|Confirmation Failed|The computed confirmation value was not successfully verified|
|0x05|Out of Resources|The provisioning protocol cannot be continued due to insufficient resources in the device|
|0x06|Decryption Failed|The Data block was not successfully decrypted|
|0x07|Unexpected Error|An unexpected error occurred that may not be recoverable|
|0x08|Cannot Assign Addresses|The device cannot assign consecutive unicast addresses to all elements|
|0x09|RFU|Reserved for Future Use|

���ˣ���������������ɡ�������ô�ಽ�����Ϊ�˻�ȡ�õ����յ�provisioning data�����ݡ���Ҳ��ζ�Ÿ�ƪ��Ҳ��������ˣ��������˾������̫�����ˣ���ʵС��д�걾ƪ����Ҳ�조���ᡱ�ˣ�Ϊ�������������������̺͸���ϸ�ڣ�����д�˿�һ�������ˣ�������������Ļ���Ӧ����ȫ������ϸ����������˵���ˡ�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/I_AM_SO_DIFFICULT.gif)