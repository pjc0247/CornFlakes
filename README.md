CornFlakes
==========

packet serializer/unserializer for ruby



sample
----
__packet_defination__
```ruby
class DummyPacket
  id PACKET_ID_DUMMY
  int dummy1
  string dummy2, 32 #string length
  string dummy3, 8
end
```


__serialize__
```ruby
pkt = DummyPacket.new
pkt.dummy1 = 1234
pkt.dummy2 = "hello world"
pkt.dummy3 = "serial"

send pkt.serialize
```


__unserialize__
```ruby
def on_recv data
  pkt = DummyPacket.unserialize data
  
  puts pkt.dummy1
  puts pkt.dummy2
  puts pkt.dummy3
end
```
