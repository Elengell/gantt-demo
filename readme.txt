��� �� �������������, ������� �� �������)

������ ��� �������� ��������� ������� �� data.json � ����� �������.
� ��������� �� ���� �������� ����, ����� ��� ���������� ������ ������������� ����� �������� � json.
������ ���� ���������� dataProcessor, ������� ���������������� � ���� "������" � ����� ������ ������ ����� � ����.
���� ������� �� ���� ������ - ������ � �����

������� "������":
id
text
start_date
duration
progress
sortorder
parent
���� - id

������� "�����":
id
source
target
type
���� - id

���� ���� ������������ � ����� connector/data.php
$res=mysql_connect("localhost","root","") or die ("Unable to connect!");
mysql_select_db("gantt");

����� ���������������� ����� � �����, � ����� index.php ����� ����������������� ������ 62-64
        gantt.load('connector/data.php');  //����������� ���� ������
	var dp = new dataProcessor("connector/data.php"); //��������� ����������� ������ ��� ������������ ����
	dp.init(gantt);  //��������� ���������� � ������� �������� ��������

� �������������� ���������������� 
	gantt.load("data.json", "json");


� ����� �������������, �� �������� �������.



��� GPL ������ ������� (���� � ������������, ���� �� ���)
���� � ����� index.html ����������������� ������ � 16� �� 57�, �� ��������� ��������������� �� ����� �� ������.
�� ���� ������� �������, �� ��� ������, ��� ������. ���������� ������ � ��������������.





p.s.
�� ������ ������ ���������� ������� sql ������� ��� ������ :)


CREATE TABLE `gantt_tasks` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `text` varchar(255) NOT NULL,
  `start_date` datetime NOT NULL,
  `duration` int(11) NOT NULL,
  `progress` float NOT NULL,
  `sortorder` int(11) NOT NULL,
  `parent` int(11) NOT NULL,
  PRIMARY KEY (`id`)
)


CREATE TABLE `gantt_links` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `source` int(11) NOT NULL,
  `target` int(11) NOT NULL,
  `type` varchar(1) NOT NULL,
  PRIMARY KEY (`id`)
)

