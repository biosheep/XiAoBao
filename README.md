using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerControl : MonoBehaviour
{
    public float maxHp = 100.0f;
    public float currentHp = 10.0f;
    public float Money ;
    private void Awake() 
    {
        currentHp =maxHp;          
    }
}

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class LeftHealth : MonoBehaviour
{
    public Image healthPointImage;
    public Image healthPointEffect;
    private PlayerControl Player;
    
    private void Awake() 
    {
        Player = GameObject.FindGameObjectWithTag("Player").GetConponent<PlayerControl>();
    }
    void Update() 
    {
        healthPointImage.fillAmount = Player.currentHp / player.maxHp;
        if(healthPointEffect.fillAmount < healthPointImage.fillAmount)
        {
            healthPointEffect.fillAmount -= 0.003f;
        }
        else
        {
            healthPointEffect.fillAmount = healthPointImage.fillAmoutn;
        }
    }
}
