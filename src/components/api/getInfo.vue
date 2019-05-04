<script>
import axios from 'axios';

export default {
    getRequest(url){
        console.log(axios.get(url).then(response => response.data))
        return axios.get(url).then(response => response.data);
    }
}
</script>