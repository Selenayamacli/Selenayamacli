-//---Hareketler---
-public class hareket : MonoBehaviour
{
    Rigidbody2D rgb;
    Vector3 velocity;
    float speedAmount = 5f;
    float jumpAmount = 8f;
    // Start is called before the first frame update
    public static int copSayisi= 0;
    void Start()
    {
        rgb = GetComponent<Rigidbody2D>();
    }

   
    void Update()
    {
        velocity = new Vector3(Input.GetAxis("Horizontal"), 0f);
        transform.position += velocity * speedAmount * Time.deltaTime;
        if (Input.GetButtonDown("Jump") && Mathf.Approximately(rgb.velocity.y, 0))
        {
            rgb.AddForce(Vector3.up * jumpAmount, ForceMode2D.Impulse);
        }

    }
}
-//---Çöpler---
public class cop : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }
    private void OnTriggerEnter2D(Collider2D collision)
    {
        Debug.Log(hareket.copSayisi);
        hareket.copSayisi++;
        GameObject.Destroy(this.gameObject);
    }
}
<!---
Selenayamacli/Selenayamacli is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
