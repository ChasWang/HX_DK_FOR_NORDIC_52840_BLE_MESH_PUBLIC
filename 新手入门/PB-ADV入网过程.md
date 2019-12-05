<!--
 * @Description: In User Settings Edit
 * @Author: ��ʱ��
 * @Date: 2019-09-13 15:08:28
 * @LastEditTime: 2019-12-05 21:39:30
 * @LastEditors: Please set LastEditors
 -->
# ǰ��
 �����ſ�������[PB-GATT��������](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/%E6%96%B0%E6%89%8B%E5%85%A5%E9%97%A8/PB-GATT%E5%85%A5%E7%BD%91%E8%BF%87%E7%A8%8B.md)�Ķ��ߣ�Ӧ�ö�������ȫ��������һ����Գ̶ȵ��˽�ɣ���Ȼ����������ڼ俴������Ҳû�й�ϵ���ǾͶ࿴���顣��������С����Ȼ���Ǹ���ҽ���Mesh������ȫ���̣�ֻ�����˴���PB-ADV�ķ�ʽ��������ô���������Ƚ���ʲô��PB-ADV��
 
 ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Time_To_Start.png)

 - ʲô��PB-ADV?

    ������һЩ�˽�Ķ��ߣ������������ʱ�϶���˵���ⲻ����ͨ���㲥�������շ����ݣ��Ӷ��������������ʵ�����ܵĸ�����˵��û�д�ġ����ǣ�������һЩ�ؼ��ĵط�������Ȼ��Ҫע�⣺
    
    1. ��PB-GATT��ͬ���ǣ�PB-ADVʹ��**Generic Provisioning PDUs**����new device,��PB-GATT����ͨ��**Proxy PDUs**������������ȫ��ͬ��PDUs��ǰ����ͨ��37��38��39�Ĺ㲥ͨ������ͨѶ������������ͨ��Proxy service���������շ���Ҳ��������ͨ������ͨѶ��
    2. PB-GATT�ǻ������ӵ�ģ�ͽ���һ���е�������������PB-ADV����ڻỰ��ģ�ͽ�����Ӧ������������ǰ�ߣ������������ݵ����PDU����ATT��MTU�Ĵ�С�������������ߵ�MTU��������ֻ��24���ֽڣ���ʹ�����ӽ������� **(Link Establishment procedure)** ���лỰ�Ľ���;

������ô�࣬���������ǻ��ǲ���ͬ������·���ȿ�PB-ADV��֡��ʽ��֮���ٷֱ���������
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/PB_ADV_Packet.png)

����ͼ��֪��PB-ADV PDU��Ҫ��**Link ID**��**Transaction Number**��**Generic Provisioning PDU**����������ɣ�

## Link ID
���ֶ�����ʾ�ĺ���ȽϺ���⣬���𵽵ľ���һ����ʶ�������ã���Ҫ���������ù��̱��ͬһ��LINK ID�£�Provisioner��unprovisioned device�����ݽ�������ͬLINK ID��packets�ᱻ�˴˺��ԣ���Ϊһ���Ự����������ʱ���ҽ���һ��Link ID,��ͬ�ĻỰ��LINK ID�ǲ�һ���ġ�**ע�⣬LINK ID����Provisioner���������**��

## Transaction Number
���ֶ���Ҫ���ڱ��ÿ��������**Generic Provisioning PDU**������0x00��ʼ����ֵ��ÿ���µ�**Generic Provisioning PDU**���ۼ� **(����Provisioning Bearer Control PDU����Transaction Numberһֱ����0x00)**������ۼӵ����ֵʱ�����ִ�0x00���¿�ʼ������Provisioner��Unprovisioned device�������ߵ����ֵ�ǲ�һ���ģ�

- Provisioner

    ���ֻ�ܴﵽ0x7F;

- Unprovisioned Device

    �����ܴﵽ0xFF;

���ǣ�Ҳ����������ǲ���Ҫ�ۼӵģ�

1. ���һ��**Provisioning PDU**�Ų���ȥʱ�����еķְ�����ͬ����**Transaction Number**�ģ�����Ҫ�ۼӣ�
2. ���**Provisioning PDU**��Ҫ���ش�����ôҲ�ǲ���Ҫ�ۼӵģ�����ʹ�þɵ�**Transaction Number**;
## Generic Provisioning PDU
��PDU����ϸ�����С�಻�ڴ˴�չ����׼���������[Generic Mesh Provisioning Control](#Generic-Mesh-Provisioning-Control)��[Generic Mesh Provisioning Payload](#Generic-Mesh-Provisioning-Payload)�����½���ϸ����
# ��������
ͬ����������������һ�½�[PB-GATT��������](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/%E6%96%B0%E6%89%8B%E5%85%A5%E9%97%A8/PB-GATT%E5%85%A5%E7%BD%91%E8%BF%87%E7%A8%8B.md)�е�**��������**С�½���ϸ����������һģһ����С������Ͳ���ϸ������ͼ��ʾ����PB-ADV��ʽ������ȫ���̣�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_Process_ADV.png)

��PB-GATT���֮�£�����**Generic Mesh Provisioning Link Open��Generic Mesh Provisioning Link Ack��Generic Mesh Provisioning Link Close**����ô������֮����ʲô�����أ�����������������Ҳ���ᵽ��һ�㣬PB-ADV�ǲ��ûỰ��ģ�ͽ����������ݵ��շ�����ô�Ựģ�;���Ҫ������PDU����������������ͼ��ʾ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Establishment_of_Link.png)

> ע�⣺������������PDU������**Provisioning Bearer Control PDU**�ķ��룬Ҳ����˵������PDU���ݲ�ͬ�ĳ�������װ�ɲ�ͬ��PDU�ͱ�ʾ**Provisioning Bearer Control PDU**��

## Generic Mesh Provisioning Link Open
Link Open��Ϣ������Provisioner��Unprovisioned Device֮�佨������,Unprovisioned Device������յ�����Ϣ��Ӧʹ��Link ACK��ϢӦ�����Ϣ�������֡��ʽ���£�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Link_Open_message.png)

����Device UUIDָ����ѡ�е�Unprovisioned Device��UUID��
## Generic Mesh Provisioning Link Ack
����Ϣ���ڷ���Ӧ����Ϣ����ʾ���յ�Link Open����Ϣ�ˣ������֡��ʽ���£�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Link_Ack_message.png)

����ֵ��ע����ǣ�Ӧ����Ϣ�ǲ�Я���κβ����ġ�
## Generic Mesh Provisioning Link Close
����Ϣ���ڹر�Link�Ự�����ڸ���Ϣ��û�б�Ӧ��ģ����Ϊ�˱��������Link�ر���Ϣ����Ҫ����3����Provisioner��Unprovisioned Device�����Է��͸���Ϣ������Я��**�ر�ԭ��**��������������֡��ʽ����ͼ��ʾ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Link_Close_message.png)

> ע�⣺����**Link Establishment procedure**���ǻ������¼�����Ҫ����˽��£�
>1. ����Provisioner���ԣ�����׼������Link�Ựʱ��������һ��60��Ķ�ʱ�������ŷ���**Link Open**��Ϣ�������60���û���յ�Unprovisioned Device��**Link Ack**����Ϣ������Ϊ�˴�Link�Ự����ʧ�ܣ�
>2. ����Unprovisioned Device���ԣ������յ�**Link Open**��Ϣ֮�󣬻��Provisioner��Ӧ**Link Ack**����Ϣ��������ͬ��Ҳ����һ��60�붨ʱ���������60���û���յ��κε�Provisioning PDU������Ϊ�˴�Link�Ự����ʧ�ܣ�

## Generic Provisioning PDU
����������֮�⣬�����ַ�ʽ���Ĳ�ͬ�ǣ�

- PB-GATT

    ͨ��**Proxy PDUs**�����������ݵ��շ�
- PB-ADV

    ͨ��**Generic Provisioning PDUs**�����������ݵ��շ�

����**Proxy PDUs**,������**PB-GATT��������**�Ѿ�ϸ��������С�½������������**Generic Provisioning PDUs**�����ݣ�����ͼ��ʾ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Generic_Provisioning_PDU.png)

����ͼ��֪����PDU��Ҫ��**Generic Provisioning Control**��**Generic Provisioning Payload**��ɡ�

### Generic Mesh Provisioning Control
���ֶ���Ҫ����Generic Provisioning Control�����������һ�����͵�GPCF,����һ�����ļ������͵�Generic Provisioning Control,������Generic Provisioning PDUʾ��ͼ�Ѿ������غ�����ˣ�

- Transaction Start             -0b00
- Transaction Acknowledgment    - 0b01
- Transaction Continuation      - 0b10
- Provisioning Bearer Control   - 0b11

#### Transaction Start
Transaction Start PDU���������ֶ���Ϣ��ת�䣬Ҳ����˵ÿһ��Provisioning PDU����Ϣ���䶼��ʹ�ø�PDU��ʼ���䡣��Provisioning PDU���׶���Щʲô֡��ʽ�أ�����һ�½�[PB-GATT��������](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/%E6%96%B0%E6%89%8B%E5%85%A5%E9%97%A8/PB-GATT%E5%85%A5%E7%BD%91%E8%BF%87%E7%A8%8B.md)���Ѿ�����������

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

��PDU�ľ���֡��ʽ���±���ʾ��

![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Transaction_Start_PDU.png)

| Field | Size (bits) |Description|
|-----|-----|-----|
|SegN|6|The last segment number|
|GPCF|2|0b00 = Transaction Start|
|TotalLength|16|The number of octets in the Provisioning PDU|
|FCS|8|Frame Check Sequence of the Provisioning PDU|

##### SegN
���ֶ���ʵ���Ǳ�ʾ����Transaction Start��Я����һЩProvisioning PDU,ʣ�µ�Provisioning PDU����Ҫ���ٸ��ֶεİ����ܷ�����ɣ�
##### GPCF
���ڸ�PDU�����ֶι̶�Ϊ0x00
#### TotalLength
��ʾҪ����Provisioning PDU���ж����ֽ�
##### FCS
���ֶ����ʾ��Provisioning PDU���м�����֡����ֵ

Ϊ��������������⣬���ǿ��Բ鿴������ʾ��׽��ͼ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Transaction_Start.png)

#### Transaction Acknowledgment
TransactionӦ��PDU����Ӧ����յ���Provisioning PDU,��������Ӧ����Ϣһ������Ҳ�ǲ�Я���κβ����ġ�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Transaction_Acknowledgment_PDU.png)

| Field | Size (bits) |Description|
|-----|-----|-----|
|Padding|6|0b000000; all other values Prohibited|
|GPCF|2|0b01 = Transaction Acknowledgment|

#### Transaction Continuation
ʹ��Transaction Start PDUû�а취������Provisioning PDU������ɣ���Ӧ��ʹ�ø��ֶδ���ְ���Provisioning PDU�������֡��ʽ������ʾ��

![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Transaction_Continuation_PDU.png)

| Field | Size (bits) |Description|
|-----|-----|-----|
|SegmentIndex|6|Segment number of the transaction|
|GPCF|2|0b10 = Transaction Continuation|

##### SegmentIndex
���ֶα�ʾ��ǰ��Provisioning PDU�ǵڼ����ְ���

##### GPCF
�̶�Ϊ0b10,��ʾTransaction Continuation��

##### Data
��ʾ�����ְ�Provisioning PDU�����ݣ�

#### Provisioning Bearer Control
�����͵�PDU��������[Generic Mesh Provisioning Link Open](#Generic-Mesh-Provisioning-Link-Open)��[Generic Mesh Provisioning Link Ack](#Generic-Mesh-Provisioning-Link-Ack)��[Generic Mesh Provisioning Link Close](#Generic-Mesh-Provisioning-Link-Close)��ͳ�ƣ���Ҳ����˵��PDU���ɸ��ݲ�ͬ��**BearerOpcode**��������ʾ��ͬ��PDU��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_Bearer_Control_PDU.png)
### Generic Mesh Provisioning Payload
���ֶ���������PDU������ʵ�Ǹ���[Generic Mesh Provisioning Control](#Generic-Mesh-Provisioning-Control)���õĲ�ͬ����ͬ���䱾�ʾ�����������Provisioning PDU��������ô���䣬������Щ�������ǿ���ǰ�����������ĸ��׶Σ�Provisioning PDU�ж����ֽڡ�**���磺��ǰProvisioner��Unprovisioned Device���뵽������Կ�Ľ׶Σ����ʱ��ͱ���ʹ��[Transaction Start PDU](#Transaction-Start-PDU)��[Transaction Continuation PDU](#Transaction-Continuation-PDU)������Provisioning PDU**��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Provisioning_Public_Key.png)


ͬʱ�������ڸտ�����[ǰ��](#ǰ��)�е�PB-ADVͼʱ���϶����ж������롰**Generic Provisioning PDU**�������ֻ֧��24�ֽ���Ϊʲô�����**Generic Provisioning Payload**��0~64�ֽڣ��ⲻ�Ǳ�24�ֽڻ����𣿡� �������������ʵĶ��ߣ�����Ӧ��֪��Ϊʲô�˰ɣ�**û���Ų���ȥ�һ����Էְ���**��

## �ܽ�
��[��������](#��������)�е���ǰ���ἰ������PB-ADV�����п��Կ����������ϸ�PB-GATT��һģһ���ģ���������½ھͲ����ظ�����ͬ�ĵ���������Ҳ�Ѿ�һһϸ�������ǻ���һЩϸ�ڣ�С����û����б�ҪҪ�˽�һ�£�

- ����ͨ�Ĺ㲥��һ����Generic Provisioning PDU�ķ���Ҳ��Ҫ����һ��20~50ms�����ʱ�䣬�����Ϳ��Դ�󽵵��ŵ���ͻ�Ŀ����ԣ��Ӷ����³���ԣ�
- ���յ�Transaction Acknowledgment����Ϣ����ʾProvisioning PDU������ɡ����������Ҫ�ְ����͵ĳ��ϣ�Unprovisioned Device������Provisioning PDU֮����Provisioner�������Ӧ�����ʱ����ܶ��߻��� **��Unprovisioned Device��ô֪���Ѿ�������Provisioning PDU�أ���**��֪�����߻���û��ӡ����[Transaction Start](#Transaction-Start)���и�**SegN**�ֶΣ�Unprovisioned Device���Ը������ж�����Provisioning PDU�Ƿ��Ѵ�����ɣ�

- ��һЩ��ҪӦ������ݽ�����˫������һ����Ϣ���ͳ�ȥ֮�������30����û���յ�Ӧ����ô�˴�����ʧ�ܣ�

- ��Unprovisioned Device������Provisioning PDU֮���������Provisioning PDU��FCS������[Transaction Start](#Transaction-Start)�е�**FCS**�ֶε�������Ƚϣ����ƥ������Ӧ����Ϣ��

- ���ҽ���Provisioner���͸�Unprovisioned Device Provisioning PDUʱ������Ҫ����Ӧ�𡣷����ǲ���Ҫ����Ӧ����Ϣ�ģ�Ҳ����˵Unprovisioned Device��Provisioner���͵���Ϣ�ǲ���Ҫ����Ӧ��ģ�
