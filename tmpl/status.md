Mirage has several backends, each of which expose a different level of I/O API depending on what the platform supports. Below is a summary, with the color indicating its implementation status (Red is under design, Orange is partially implemented, and Green means it is working).

Keep an eye on the [blog](/blog) for more details about what some of these actually mean, over the next few weeks.

<table class="impl">
 <tr>
  <th> Target </th>
  <th> Memory </th>
  <th> Timer </th>
  <th> Network </th>
  <th> Storage </th>
 </tr>
 <tr>
  <td class="impl_orange"> Xen </td>
  <td class="impl_orange"> x86_64 pagetable </td>
  <td class="impl_green"> tickless domain block </td>
  <td class="impl_orange"> ethernet AIO </td>
  <td class="impl_orange"> block AIO </td>
 </tr>
 <tr>
  <td class="impl_orange"> Linux low-level </td>
  <td class="impl_green"> malloc </td>
  <td class="impl_green"> select </td>
  <td class="impl_orange"> tuntap ethernet AIO </td>
  <td class="impl_red"> mmap block AIO </td>
 </tr>
 <tr>
  <td class="impl_orange"> Linux </td>
  <td class="impl_red"> hugetlbfs </td>
  <td class="impl_red"> epoll </td>
  <td class="impl_orange"> async sockets </td>
  <td class="impl_red"> mmap block AIO </td>
 </tr>
 <tr>
  <td class="impl_orange"> Browser </td>
  <td class="impl_green"> Javascript </td>
  <td class="impl_green"> DOM callback </td>
  <td class="impl_red"> websockets </td>
  <td class="impl_red"> SQL localstorage </td>
 </tr>
</table>