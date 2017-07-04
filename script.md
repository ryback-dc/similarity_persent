# similarity_persent

<?php

function persentase_perbandingan ($str1, $str2) {
          $len1       = strlen($str1);
          $len2       = strlen($str2);
          //echo $str1.'--'.$str2.'--';
          $max        = max($len1, $len2);
          $similarity = 0;
          $i          = 0;
          $j          = 0;
          while (($i < $len1) && isset($str2[$j])) {
                  if (@$str1[$i] == @$str2[$j]) {
                          $similarity++;
                          $i++;
                          $j++;
                  } elseif ($len1 < $len2) {
                          $len1++;
                          $j++;
                  } elseif ($len1 > $len2) {
                          $i++;
                          $len1--;
                  } else {
                          $i++;
                          $j++;
                  }
         }
         $return  = round($similarity/$len1*100);
         return $return .'%';

}

$data_customer = 'VFS SERVICES INDONESIA, PT';
$data_master_1 = 'VS SERCES IDOESIA, PT';

echo persentase_perbandingan($data_customer, $data_master_1);

?>
